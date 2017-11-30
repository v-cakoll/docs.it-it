---
title: 'Procedura: convertire un oggetto in un altro tipo in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Procedura: convertire un oggetto in un altro tipo in Visual Basic
Convertire un `Object` variabile a un altro tipo di dati tramite una parola chiave di conversione, ad esempio [CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente converte un `Object` variabile a un `Integer` e `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Se si è certi che il contenuto di un `Object` sono variabile di un particolare tipo di dati, si consiglia di convertire la variabile di quel tipo di dati. Se si continua a utilizzare il `Object` variabile, verrà eseguita una *boxing* e *unboxing* (per un tipo di valore) o *ad associazione tardiva* (per un tipo di riferimento). Queste operazioni tutti richiedere più tempo di esecuzione e riduzione delle prestazioni.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Object>  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversioni fra stringhe e altri tipi](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
