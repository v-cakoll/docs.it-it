---
title: Tipo di dati Boolean (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc106f1ec874c1a2165df069d5f3485fe5b2e43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-data-type-visual-basic"></a>Tipo di dati Boolean (Visual Basic)
Contiene valori che possono essere solo `True` o `False`. Le parole chiave `True` e `False` corrispondono a due stati di `Boolean` variabili.  
  
## <a name="remarks"></a>Note  
 Utilizzare il [tipo di dati Boolean (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) per contenere i valori di due stati, ad esempio true/false, sì/no o on/off.  
  
 Il valore predefinito di `Boolean` è `False`.  
  
 `Boolean`i valori non vengono archiviati come numeri e i valori archiviati non sono considerati equivalenti ai numeri. Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False`. Quando possibile, è consigliabile limitare l'utilizzo di `Boolean` variabili per i valori logici per cui vengono progettate.  
  
## <a name="type-conversions"></a>Conversione di tipi  
 Quando Visual Basic converte i valori di tipo di dati numerici in `Boolean`, diventa 0 `False` e tutti gli altri valori diventano `True`. Quando Visual Basic converte `Boolean` valori per i tipi numerici, `False` diventa 0 e `True` diventa -1.  
  
 Quando esegue la conversione tra `Boolean` valori e tipi di dati numerici, tenere presente che i metodi di conversione di .NET Framework non producono sempre gli stessi risultati di parole chiave di conversione di Visual Basic. Questo avviene perché la conversione di Visual Basic mantiene un comportamento compatibile con le versioni precedenti. Per ulteriori informazioni, vedere "Booleano tipo non di numerico tipo accuratezza durante la conversione" in [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Numeri negativi.** `Boolean`non è un tipo numerico e non può rappresentare un valore negativo. In ogni caso, è consigliabile non utilizzare `Boolean` per contenere valori numerici.  
  
-   **Caratteri tipo.** `Boolean`non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `runningVB` è un `Boolean` variabile, che memorizza una semplice impostazione sì/no.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)
