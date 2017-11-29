---
title: 'Procedura: dichiarare una struttura (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8203327e189d095c9f7ceeb3b68ea24efe9ba882
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Procedura: dichiarare una struttura (Visual Basic)
Iniziare con una dichiarazione di struttura di [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), e terminano con il `End` `Structure` istruzione. Tra queste due istruzioni è necessario dichiarare almeno un *elemento*. Gli elementi possono essere di qualsiasi tipo di dati, ma almeno uno deve essere una variabile non condivisa o un evento e non condiviso.  
  
 Non è possibile inizializzare uno degli elementi di struttura nella dichiarazione della struttura. Quando si dichiara una variabile per un tipo di struttura, è possibile accedervi tramite la variabile per assegnare valori agli elementi.  
  
 Per una descrizione delle differenze tra classi e strutture, vedere [strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 A scopo dimostrativo, si consideri una situazione in cui si desidera tenere traccia di nome, numero di telefono e stipendio del dipendente. Una struttura consente di eseguire questa operazione in una singola variabile.  
  
### <a name="to-declare-a-structure"></a>Per dichiarare una struttura  
  
1.  Creare l'inizio e fine delle istruzioni per la struttura.  
  
     È possibile specificare il livello di accesso di una struttura utilizzando il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privata](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave), oppure è possibile attenderne Per impostazione predefinita `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Aggiungere elementi al corpo della struttura.  
  
     Una struttura deve contenere almeno un elemento. È necessario dichiarare ogni elemento e specificare un livello di accesso per questo file. Se si utilizza il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) senza alcuna parola chiave, l'accessibilità per impostazione predefinita `Public`.  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     Il `salary` campo nell'esempio precedente è `Private`, vale a dire che non è accessibile dall'esterno della struttura, anche da una classe che lo contiene. Tuttavia, il `giveRaise` procedura `Public`, pertanto può essere chiamata dall'esterno della struttura. Analogamente, è possibile generare il `salaryReviewTime` evento dall'esterno della struttura.  
  
     Oltre alle variabili, `Sub` procedure e gli eventi, è inoltre possibile definire le costanti, `Function` procedure e le proprietà in una struttura. È possibile definire al massimo una proprietà come il *proprietà predefinita*, se è necessario almeno un argomento. È possibile gestire un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedura. Per ulteriori informazioni, vedere [procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Variabili di struttura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Tipo di dati definito dall'utente](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
