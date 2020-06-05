---
title: Assembly
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7d313dee1015362bd0215ed98ab7e898312cfbcd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373160"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Specifica che un attributo all'inizio di un file di origine viene applicato all'intero assembly.  
  
## <a name="remarks"></a>Commenti  
 Molti attributi riguardano un singolo elemento di programmazione, ad esempio una classe o una proprietà. Applicare tale attributo alleghindo il blocco di attributi, racchiuso tra parentesi acute ( `< >` ), direttamente all'istruzione di dichiarazione.  
  
 Se un attributo riguarda non solo l'elemento seguente ma l'intero assembly, inserire il blocco di attributi all'inizio del file di origine e identificare l'attributo con la `Assembly` parola chiave. Se si applica al modulo di assembly corrente, usare la parola chiave [Module](module-keyword.md) .  
  
 È anche possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario usare un blocco di attributi nel file del codice sorgente principale.  
  
## <a name="see-also"></a>Vedere anche

- [Modulo\<keyword>](module-keyword.md)
- [Panoramica degli attributi](../../programming-guide/concepts/attributes/index.md)
