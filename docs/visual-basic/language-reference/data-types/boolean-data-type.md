---
title: Tipo di dati booleani
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347853"
---
# <a name="boolean-data-type-visual-basic"></a>Tipo di dati Boolean (Visual Basic)

Include valori che possono essere solo `True` o `False`. Le parole chiave `True` e `False` corrispondono ai due Stati delle variabili di `Boolean`.  
  
## <a name="remarks"></a>Note  

 Usare il [tipo di dati booleano (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) per contenere valori a due Stati, ad esempio true/false, Yes/No o on/off.  
  
 Il valore predefinito di `Boolean` è `False`.  
  
 `Boolean` valori non vengono archiviati come numeri e i valori archiviati non sono destinati a essere equivalenti ai numeri. Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False`. Laddove possibile, è consigliabile limitare l'utilizzo delle variabili di `Boolean` ai valori logici per i quali sono stati progettati.  
  
## <a name="type-conversions"></a>Conversione di tipi  

 Quando Visual Basic converte i valori dei tipi di dati numerici in `Boolean`, 0 diventa `False` e tutti gli altri valori diventano `True`. Quando Visual Basic converte i valori di `Boolean` in tipi numerici, `False` diventa 0 e `True` diventa-1.  
  
 Quando si esegue la conversione tra `Boolean` valori e tipi di dati numerici, tenere presente che i metodi di conversione .NET Framework non producono sempre gli stessi risultati delle parole chiave di conversione Visual Basic. Ciò è dovuto al fatto che la conversione Visual Basic mantiene il comportamento compatibile con le versioni precedenti. Per ulteriori informazioni, vedere "il tipo booleano non viene convertito in un tipo numerico con precisione" nella [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
- **Numeri negativi.** `Boolean` non è un tipo numerico e non può rappresentare un valore negativo. In ogni caso, non utilizzare `Boolean` per mantenere i valori numerici.  
  
- **Digitare i caratteri.** `Boolean` non ha un carattere di tipo letterale o un carattere di tipo identificatore.  
  
- **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  

 Nell'esempio seguente `runningVB` è una variabile `Boolean`, che archivia una semplice impostazione Sì/No.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Boolean?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
