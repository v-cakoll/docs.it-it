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
ms.openlocfilehash: 1385919a1205a60104125fff1bdd24f409a091df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351641"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Specifica che un attributo all'inizio di un file di origine viene applicato all'intero assembly.  
  
## <a name="remarks"></a>Note  
 Molti attributi riguardano un singolo elemento di programmazione, ad esempio una classe o una proprietà. Applicare tale attributo alleghindo il blocco di attributi, racchiuso tra parentesi angolari (`< >`), direttamente all'istruzione di dichiarazione.  
  
 Se un attributo riguarda non solo l'elemento seguente ma l'intero assembly, il blocco di attributi viene inserito all'inizio del file di origine e l'attributo viene identificato con la parola chiave `Assembly`. Se si applica al modulo di assembly corrente, usare la parola chiave [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) .  
  
 È anche possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario usare un blocco di attributi nel file del codice sorgente principale.  
  
## <a name="see-also"></a>Vedere anche

- [Modulo \<parola chiave>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
