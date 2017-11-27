---
title: Value Types and Reference Types
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b54945d27d186771e8b5353e753afd74c56d71b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
In Visual Basic, i tipi di dati vengono implementati in base alla relativa classificazione. Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tipi di dati possono essere classificati in base a una variabile di un particolare tipo di archiviazione o meno i propri dati o un puntatore ai dati. Se archivia i propri dati è un *tipo di valore*; se contiene un puntatore ai dati in un' posizione in memoria è un *tipo di riferimento*.  
  
## <a name="value-types"></a>Tipi valore  
 Un tipo di dati è un *tipo di valore* se contiene i dati nella propria allocazione di memoria. Tipi di valore sono i seguenti:  
  
-   Tutti i tipi di dati numerici  
  
-   `Boolean`, `Char` e `Date`  
  
-   Tutte le strutture, anche se i relativi membri sono tipi di riferimento  
  
-   Le enumerazioni, poiché il relativo tipo sottostante è sempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, o`ULong`  
  
 Ogni struttura è un tipo valore, anche se contiene membri di tipo riferimento. Per questo motivo, i tipi valore come `Char` e `Integer` vengono implementati dalle strutture di .NET Framework.  
  
 È possibile dichiarare un tipo di valore utilizzando la parola chiave riservata, ad esempio, `Decimal`. È inoltre possibile utilizzare il `New` (parola chiave) per inizializzare un tipo di valore. Ciò è particolarmente utile se il tipo ha un costruttore che accetta parametri. Un esempio di questo è il <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> costruttore, che genera un nuovo `Decimal` valore dalle parti fornite.  
  
## <a name="reference-types"></a>Tipi riferimento  
 Oggetto *tipo di riferimento* contiene un puntatore a un'altra posizione di memoria che contiene i dati. I tipi di riferimento includono:  
  
-   `String`  
  
-   Tutte le matrici, anche se i relativi elementi sono tipi di valore  
  
-   Tipi di classe, ad esempio<xref:System.Windows.Forms.Form>  
  
-   Delegati  
  
 Una classe è un *tipo di riferimento*. Per questo motivo, tipi di riferimento, ad esempio `Object` e `String` sono supportati da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classi. Si noti che ogni matrice è un tipo riferimento, anche se i relativi membri sono tipi di valore.  
  
 Poiché ogni tipo di riferimento rappresenta una classe sottostante di .NET Framework, è necessario utilizzare il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave quando la si inizializza. L'istruzione seguente consente di inizializzare una matrice.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elementi che non sono tipi  
 I seguenti elementi di programmazione non è qualificano come tipi, perché non è possibile specificare uno di essi come tipo di dati per un elemento dichiarato:  
  
-   Spazi dei nomi  
  
-   Moduli  
  
-   Eventi  
  
-   Proprietà e routine  
  
-   Le variabili, costanti e campi  
  
## <a name="working-with-the-object-data-type"></a>Utilizzo del tipo di dati oggetto  
 È possibile assegnare un tipo riferimento o un tipo di valore a una variabile del `Object` tipo di dati. Un `Object` variabile contiene sempre un puntatore ai dati, mai i dati stessi. Tuttavia, se si assegna un tipo di valore a un `Object` variabile, si comporta come se contenesse i propri dati. Per ulteriori informazioni, vedere [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 È possibile scoprire se un `Object` variabile funge da un tipo riferimento o un tipo di valore passandola al <xref:Microsoft.VisualBasic.Information.IsReference%2A> metodo il <xref:Microsoft.VisualBasic.Information> classe del <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>Restituisce `True` se il contenuto del `Object` variabile rappresenta un tipo di riferimento.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di valori nullable](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Uso efficiente dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
