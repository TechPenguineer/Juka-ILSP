# Juka ILSP
 Juka Languages Integrated Language Server Protocol

Juka’s integrated language server protocol ( ILSP ) is what Juka Application’s use to handle the parsing, tokenizing, and HEX assigning to user input. It is able to complete such task’s by using the following algorithm 

![FLOW_CHART.png](https://cdn.discordapp.com/attachments/998676260064596058/1005631330442301480/unknown.png)

 It starts by having an event system that is called everytime the editor detects a change in user input. It then parses the data, and passes it as an argument to the LSP. The LSP will search for the defined token’s in categories show in the flow chart. It will create an array with formatted with the following key pairs:


`[ {TOKEN_LOCATION}, {DFEINED_HEX} ]`


The LSP will automatically fine the term by the “TOKEN_LOCATION” value. The Token Location variable will store the index of which it occurs in the parsed data array. The HEX will automatically be paired from a preset definition. 

How does it assign multi color to MAUI. The actual editor for the Juka App is not seen. What you are seeing is a mock of what is in the editor where each word in the parsed data is represented by a label element that can be used as a separate colour. 



## Example Token Search:
```
FUNCTION_HEX = "#6a90cc";
TOKEN_LOCATION;

juka.ilsp.searchForToken(type="function", assign_hex = FUNCTION_HEX);
```

## Example Data Parser:

```
juka.ilsp.parse(DATA);
```

## Example Edit Colour Value:

```
juka.ilsp.color.edit(type='VAR_ASSIGNMENT', changeTo="#6accc9");
```

## Example Add Type:
```
juka.ilsp.structure.addType(type="ASSIGN_INT", tokenToSearch="int", hex="#6a95cc");
```
