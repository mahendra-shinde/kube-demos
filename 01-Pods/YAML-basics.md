## YAML is Alternative for JSON
## YAML is EASIER to PROCESS for APPLICATIONS
## YAML is lightweight Alternative to JSON

# Simple JSON String 

{
    "name":"mahendra" 
}

# Simple YAML String
name: mahendra

# KEY must be followed with ":" , ensure there is a SPACE after ":"
# String VALUE with NO SPACES DOESN'T NEED Single or Double Quote
# String VALUE with SPACE requires QUOTES

name: 'Mahendra Shinde'

# Simple INT Values (Same String)
age: 36

# Single FLOAT values (Single Quotes requires)
pi: '3.14'

## Properties:
{
    "author":
        {
            "name": "Mahendra Shinde"
        }
}

## Propeties in YAML
author:
  name: 'Mahendra Shinde'

## Nested Properties
{
    "application":
    {
        "instances":
        [
            {
            "id": 1,
            "node": 'node1'
            },
            {
            "id": 2,
            "node": 'node2'
            }
        ]
    }
}

## YAML
application: 
  instances:
  - id: 1
    node: node1
  - id: 2
    node: node2  

## application.instances[0].id=1



