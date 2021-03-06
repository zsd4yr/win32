---
title: ret - vs
description: Return from a subroutine or a main function.
ms.assetid: ee3a6a7a-c068-442f-9f86-c637b5707224
ms.topic: article
ms.date: 05/31/2018
topic_type: 
- kbArticle
api_name: 
api_type: 
api_location: 
---

# ret - vs

Return from a subroutine or a main function.

## Syntax



| ret |
|-----|



 

## Remarks



| Vertex shader versions | 1\_1 | 2\_0 | 2\_x | 2\_sw | 3\_0 | 3\_sw |
|------------------------|------|------|------|-------|------|-------|
| ret                    |      | x    | x    | x     | x    | x     |



 

This instruction takes the address of an instruction from the return address stack and continues execution from it. In the case of the main function, this instruction stops shader execution.

The ret instruction consumes one vertex shader instruction slot.

If a shader contains no subroutines, using ret at the end of the main program is optional.

Multiple return statements are not permitted in the main program or in any subroutine, the first return statement is treated as the end of the main program or subroutine.

## Related topics

<dl> <dt>

[Vertex Shader Instructions](dx9-graphics-reference-asm-vs-instructions.md)
</dt> </dl>

 

 




