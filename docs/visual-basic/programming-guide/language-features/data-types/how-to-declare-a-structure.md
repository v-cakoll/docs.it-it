---
title: 'Procedura: dichiarare una struttura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: c3090b5b8e53e5a5a990ae11c91464797bde9803
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582310"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Procedura: dichiarare una struttura (Visual Basic)
Si inizia una dichiarazione di struttura con l' [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)e la si termina con l'istruzione `End Structure`. Tra queste due istruzioni è necessario dichiarare almeno un *elemento*. Gli elementi possono essere di qualsiasi tipo di dati, ma almeno uno deve essere una variabile non condivisa o un evento non condiviso non personalizzato.  
  
 Non è possibile inizializzare alcuno degli elementi della struttura nella dichiarazione della struttura. Quando si dichiara una variabile come un tipo di struttura, si assegnano valori agli elementi accedendo tramite la variabile.  
  
 Per informazioni sulle differenze tra le strutture e le classi, vedere [strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 A scopo dimostrativo, si consideri una situazione in cui si desidera tenere traccia del nome di un dipendente, dell'estensione telefonico e dello stipendio. Una struttura consente di eseguire questa operazione in una singola variabile.  
  
### <a name="to-declare-a-structure"></a>Per dichiarare una struttura  
  
1. Creare le istruzioni iniziali e finali per la struttura.  
  
     È possibile specificare il livello di accesso di una struttura usando la parola chiave [public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)o [private](../../../../visual-basic/language-reference/modifiers/private.md) oppure è possibile consentire l'impostazione predefinita `Public`.  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Aggiungere elementi al corpo della struttura.  
  
     Una struttura deve contenere almeno un elemento. È necessario dichiarare ogni elemento e specificare un livello di accesso. Se si usa l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) senza parole chiave, l'impostazione predefinita dell'accessibilità è `Public`.  
  
    ```vb  
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
  
     Il `salary` campo nell'esempio precedente è `Private`, il che significa che non è accessibile all'esterno della struttura, anche dalla classe che lo contiene. Tuttavia, la procedura `giveRaise` è `Public`, quindi può essere chiamata dall'esterno della struttura. Analogamente, è possibile generare l'evento `salaryReviewTime` dall'esterno della struttura.  
  
     Oltre alle variabili, `Sub` procedure ed eventi, è anche possibile definire costanti, procedure `Function` e proprietà in una struttura. È possibile designare al massimo una proprietà come *proprietà predefinita*, purché accetti almeno un argomento. È possibile gestire un evento con una procedura di `Sub` [condivisa](../../../../visual-basic/language-reference/modifiers/shared.md) . Per altre informazioni, vedere [procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Variabili di struttura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Tipo di dati definito dall'utente](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
