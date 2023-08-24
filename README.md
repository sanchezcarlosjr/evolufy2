# Evolufy
A Browser-based Investment Portfolio Optimization Library Utilizing Genetic Algorithms and Transfomers for Sustainable Decision-making

[Check out my Thesis to know more](https://carlos-eduardo-sanchez-torres.sanchezcarlosjr.com/Evolufy-Making-Sustainable-Finance-a-Reality-with-a-Web-based-Investment-Portfolio-Library-that-Uti-c3a1983ae6d24851b979d114b3784c2d)

# Datasets
## Mexico Issuers
We got the Mexico issuers dataset from [emisoras](https://databursatil.com/docs.html#emisoras) after applying

```bash
[.[] | to_entries[] | .value[] + {"Nombre": .key}]
```

## History
We got the Mexico prices history dataset from [historicos](https://databursatil.com/docs.html#historicos) after applying
```bash
[.[] 
| to_entries[] 
| .value[] + {"Nombre": .key} 
| select( .Estatus | contains("ACTIVA")) 
| "\(.Nombre)\(.Serie)"
] 
```
