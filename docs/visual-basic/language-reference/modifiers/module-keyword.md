---
title: Modulo<keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 0cb009c22dada7b92956e113d33505923a92f2b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362424"
---
# <a name="module-keyword-visual-basic"></a>Modulo \<keyword> (Visual Basic)
Specifica che un attributo all'inizio di un file di origine viene applicato al modulo di assembly corrente.  
  
## <a name="remarks"></a>Commenti  
 Molti attributi riguardano un singolo elemento di programmazione, ad esempio una classe o una proprietà. Applicare tale attributo alleghindo il blocco di attributi, racchiuso tra parentesi acute ( `< >` ), direttamente all'istruzione di dichiarazione.  
  
 Se un attributo riguarda non solo l'elemento seguente ma al modulo di assembly corrente, il blocco di attributi viene inserito all'inizio del file di origine e l'attributo viene identificato con la `Module` parola chiave. Se si applica all'intero assembly, usare la parola chiave [assembly](assembly.md) .  
  
 Il `Module` modificatore non è uguale all' [istruzione Module](../statements/module-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Assembly](assembly.md)
- [Istruzione Module](../statements/module-statement.md)
- [Panoramica degli attributi](../../programming-guide/concepts/attributes/index.md)
