---
title: Tipo di dati Boolean
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
ms.openlocfilehash: 851c524a83c5f24b77a151634a96798249c5905e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374421"
---
# <a name="boolean-data-type-visual-basic"></a>Tipo di dati Boolean (Visual Basic)

Include valori che possono essere solo `True` o `False` . Le parole chiave `True` e `False` corrispondono ai due stati di `Boolean` variabili.  
  
## <a name="remarks"></a>Commenti  

 Usare il [tipo di dati booleano (Visual Basic)](boolean-data-type.md) per contenere valori a due Stati, ad esempio true/false, Yes/No o on/off.  
  
 Il valore predefinito di `Boolean` è `False`.  
  
 `Boolean`i valori non vengono archiviati come numeri e i valori archiviati non sono destinati a essere equivalenti ai numeri. Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False` . Laddove possibile, è consigliabile limitare l'utilizzo delle `Boolean` variabili ai valori logici per i quali sono stati progettati.  
  
## <a name="type-conversions"></a>Conversione di tipi  

 Quando Visual Basic converte i valori del tipo di dati numerico in `Boolean` , 0 diventa `False` e tutti gli altri valori diventano `True` . Quando Visual Basic converte `Boolean` i valori in tipi numerici, `False` diventa 0 e `True` diventa-1.  
  
 Quando si esegue la conversione tra `Boolean` valori e tipi di dati numerici, tenere presente che i metodi di conversione .NET Framework non producono sempre gli stessi risultati delle parole chiave di conversione di Visual Basic. Ciò è dovuto al fatto che la conversione Visual Basic mantiene il comportamento compatibile con le versioni precedenti. Per ulteriori informazioni, vedere "il tipo booleano non viene convertito in un tipo numerico con precisione" nella [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
- **Numeri negativi.** `Boolean`non è un tipo numerico e non può rappresentare un valore negativo. In ogni caso, è consigliabile non usare `Boolean` per mantenere i valori numerici.  
  
- **Digitare i caratteri.** `Boolean`non ha un carattere di tipo letterale o un carattere di tipo identificatore.  
  
- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  

 Nell'esempio seguente `runningVB` è una `Boolean` variabile che archivia una semplice impostazione Yes/No.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Boolean?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../functions/ctype-function.md)
