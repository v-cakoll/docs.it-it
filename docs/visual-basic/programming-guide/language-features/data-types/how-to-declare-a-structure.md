---
title: 'Procedura: Dichiarare una struttura'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a6b70d0973e92db90e35e61b7fed2279c5b0bac3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393974"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Procedura: dichiarare una struttura (Visual Basic)
Si inizia una dichiarazione di struttura con l' [istruzione Structure](../../../language-reference/statements/structure-statement.md)e la si termina con l' `End Structure` istruzione. Tra queste due istruzioni è necessario dichiarare almeno un *elemento*. Gli elementi possono essere di qualsiasi tipo di dati, ma almeno uno deve essere una variabile non condivisa o un evento non condiviso non personalizzato.  
  
 Non è possibile inizializzare alcuno degli elementi della struttura nella dichiarazione della struttura. Quando si dichiara una variabile come un tipo di struttura, si assegnano valori agli elementi accedendo tramite la variabile.  
  
 Per informazioni sulle differenze tra le strutture e le classi, vedere [strutture e classi](structures-and-classes.md).  
  
 A scopo dimostrativo, si consideri una situazione in cui si desidera tenere traccia del nome di un dipendente, dell'estensione telefonico e dello stipendio. Una struttura consente di eseguire questa operazione in una singola variabile.  
  
### <a name="to-declare-a-structure"></a>Per dichiarare una struttura  
  
1. Creare le istruzioni iniziali e finali per la struttura.  
  
     È possibile specificare il livello di accesso di una struttura utilizzando la parola chiave [public](../../../language-reference/modifiers/public.md), [protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)o [private](../../../language-reference/modifiers/private.md) oppure è possibile consentire l'impostazione predefinita di `Public` .  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Aggiungere elementi al corpo della struttura.  
  
     Una struttura deve contenere almeno un elemento. È necessario dichiarare ogni elemento e specificare un livello di accesso. Se si usa l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) senza parole chiave, l'impostazione predefinita dell'accessibilità è `Public` .  
  
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
  
     Il `salary` campo nell'esempio precedente è `Private` , il che significa che non è accessibile all'esterno della struttura, anche dalla classe che lo contiene. Tuttavia, la `giveRaise` procedura è `Public` , quindi può essere chiamata dall'esterno della struttura. Analogamente, è possibile generare l' `salaryReviewTime` evento dall'esterno della struttura.  
  
     Oltre a variabili, `Sub` routine ed eventi, è anche possibile definire costanti, `Function` procedure e proprietà in una struttura. È possibile designare al massimo una proprietà come *proprietà predefinita*, purché accetti almeno un argomento. È possibile gestire un evento con una procedura [condivisa](../../../language-reference/modifiers/shared.md) `Sub` . Per altre informazioni, vedere [procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Tipi di dati elementari](elementary-data-types.md)
- [Tipi di dati compositi](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Strutture](structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Variabili di struttura](structure-variables.md)
- [Strutture e altri elementi di programmazione](structures-and-other-programming-elements.md)
- [Strutture e classi](structures-and-classes.md)
- [Tipo di dati definito dall'utente](../../../language-reference/data-types/user-defined-data-type.md)
