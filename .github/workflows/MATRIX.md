

```yaml
Name: Matrix example

on: 
 push: 
    branch: main

jobs: 
  matrix:
    name: 'matrix-with-includes'
    environment:
      name: dev
    runs-on: ubuntu-latest
    strategy:
        matrix:
            greetings: ["Hello", "Hi"]
            names: ["Adam", "Eve"]
            saying: ["Better safe than sorry", "Better late than never"]
            include:
                - book: "bible" ## Added to all matrix combinations
                - gender: "male" ## Adds "gender=male" to all matrix combinations with "names" == "Adam"
                  names: "Adam"
                - gender: "female" ## Adds "gender=female" to all matrix combinations with "names" == "Eve"
                  names: "Eve"
                - greetings: "Hej" ## Adds an additional matrix combination with "greetings" == "Hej" only
                - names: "Adam" ## Added as an additional matrix combination with "names" == "Adam" and "gender" == "male" and "saying" == "Should have known better"
                  gender: "male" 
                  saying: "Should have known better" 
        fail-fast: true
        max-parallel: 1
    steps:
      - name: Echo out
        run: echo '${{ matrix.greetings }} ${{ matrix.names }} ${{matrix.saying}} ${{ matrix.book }} ${{matrix.gender}}'
   
   ## Resulting output:
      ## Hello Adam Better safe than sorry bible male
      ## Hello Adam Better late than never bible male
      ## Hello Eve Better safe than sorry bible female
      ## Hello Eve Better late than never bible female
      ## Hi Adam Better safe than sorry bible male
      ## Hi Adam Better late than never bible male
      ## Hi Eve Better safe than sorry bible female
      ## Hi Eve Better late than never bible female
      ## Hej
      ## Adam Should have known better  male
```