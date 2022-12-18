# A List of Helpful Anisble Commands & Resources
------------------------------------------------

### Common Patterns Table

| Pattern | Results |
| ----------- | ----------- |
| all | all hosts from your inventory file |
| host1 | a single (host1) |
| host1:host2 | both host1 and host2 |
| group1:group2 | all servers in group1 and group2 |
| group1:\&group2 | only servers in both group1 and group2 |
| group1:\!group2 | servers in group1 except those also in group2 |


### List machines in your inventory file

``` JavaScript
ansible-inventory -i inventory --list
```

### Execute commands and playbooks with custom inventories

``` JavaScript
ansible all -i inventory -m ping
```
```
ansible-playbook -i inventory playbook.yml
```

### Target servers in database production groups

``` JavaScript
ansible dbservers:\&production -m ping
```

### Target servers in db but not prod

``` JavaScript
ansible dbservers:\!production -m ping
```


### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```
