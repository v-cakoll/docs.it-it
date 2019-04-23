---
title: 'Procedura: Dichiarare una struttura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343558"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Procedura: Dichiarare una struttura (Visual Basic)
Iniziare una dichiarazione structure con la [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), e terminano con il `End Structure` istruzione. Tra le due istruzioni seguenti è necessario dichiarare almeno *elemento*. Gli elementi possono essere di qualsiasi tipo di dati, ma almeno uno deve essere una variabile non condivisa o un evento e non condiviso.  
  
 Non è possibile inizializzare uno degli elementi struttura nella dichiarazione di struttura. Quando si dichiara una variabile di un tipo di struttura, è possibile accedervi tramite la variabile per assegnare valori agli elementi.  
  
 Per una descrizione delle differenze tra classi e strutture, vedere [classi e strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 A scopo dimostrativo, si consideri una situazione in cui si vuole tenere traccia di nome, numero di telefono e stipendio del dipendente. Una struttura consente di eseguire questa operazione in una singola variabile.  
  
### <a name="to-declare-a-structure"></a>Per dichiarare una struttura  
  
1. Creazione di inizio e fine delle istruzioni per la struttura.  
  
     È possibile specificare il livello di accesso di una struttura con il [pubbliche](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privato](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave), oppure è possibile lasciare che Per impostazione predefinita `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. Aggiungere elementi al corpo della struttura.  
  
     Una struttura deve avere almeno un elemento. È necessario dichiarare ogni elemento e specificare un livello di accesso per esso. Se si usa la [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) senza alcuna parola chiave, per impostazione predefinita l'accessibilità `Public`.  
  
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
  
     Il `salary` campo nell'esempio precedente è `Private`, vale a dire che è accessibile dall'esterno della struttura, anche dalla classe che contiene. Tuttavia, il `giveRaise` routine `Public`, pertanto può essere chiamato dall'esterno della struttura. Analogamente, è possibile generare il `salaryReviewTime` evento dall'esterno della struttura.  
  
     Oltre alle variabili, `Sub` routine ed eventi, è anche possibile definire le costanti, `Function` procedure e le proprietà in una struttura. È possibile definire al massimo una proprietà come il *predefiniti delle proprietà*, a condizione che richiede almeno un argomento. È possibile gestire un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedure. Per altre informazioni, vedere [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Variabili di struttura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Tipo di dati definito dall'utente](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
