---
title: Assembly (Visual Basic)
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
ms.openlocfilehash: e6cb7e7a2520d6bb586dab4ed0af75abb04fabd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726468"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Specifica che un attributo all'inizio di un file di origine si applica all'intero assembly.  
  
## <a name="remarks"></a>Note  
 Numero di attributi si riferiscono a un singolo elemento di programmazione, ad esempio una classe o proprietà. Per applicare tale attributo, collegare il blocco di attributi, parentesi angolari (`< >`), direttamente nell'istruzione di dichiarazione.  
  
 Se un attributo relativo non solo per l'elemento seguente ma all'intero assembly, inserire il blocco di attributi all'inizio del file di origine e di identificare l'attributo con il `Assembly` (parola chiave). Se si applica al modulo dell'assembly corrente, usare il [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) (parola chiave).  
  
 È anche possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario usare un blocco di attributi nel file di codice sorgente principale.  
  
## <a name="see-also"></a>Vedere anche
- [Modulo \<parola chiave>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)

