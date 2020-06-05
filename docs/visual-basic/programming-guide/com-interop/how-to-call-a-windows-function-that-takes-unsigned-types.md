---
title: 'Procedura: Chiamare una funzione Windows che accetta tipi senza segno'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: f30b78a2f0c38f233796e18006c889438dce4c58
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396830"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Procedura: chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)

Se si utilizza una classe, un modulo o una struttura con membri di tipi di Unsigned Integer, è possibile accedere a questi membri con Visual Basic.

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Per chiamare una funzione Windows che accetta un tipo senza segno

1. Utilizzare un' [istruzione Declare](../../language-reference/statements/declare-statement.md) per indicare Visual Basic quale libreria include la funzione, il nome della libreria, il tipo di sequenza chiamante e come convertire le stringhe quando viene chiamato.

2. Nell' `Declare` istruzione usare,, `UInteger` `ULong` `UShort` o `Byte` come appropriato per ogni parametro con un tipo senza segno.

3. Consultare la documentazione per la funzione di Windows che si sta chiamando per trovare i nomi e i valori delle costanti che usa. Molti di questi vengono definiti nel file WinUser. h.

4. Dichiarare le costanti necessarie nel codice. Molte costanti di Windows sono valori senza segno a 32 bit ed è necessario dichiararle `As UInteger` .

5. Chiamare la funzione in modo normale. Nell'esempio seguente viene chiamata la funzione di Windows `MessageBox` , che accetta un argomento Unsigned Integer.

    ```vb
    Public Class windowsMessage
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (
            ByVal hWnd As Integer,
            ByVal lpText As String,
            ByVal lpCaption As String,
            ByVal uType As UInteger) As Integer
        Private Const MB_OK As UInteger = 0
        Private Const MB_ICONEXCLAMATION As UInteger = &H30
        Private Const IDOK As UInteger = 1
        Private Const IDCLOSE As UInteger = 8
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION
        Public Function messageThroughWindows() As String
            Dim r As Integer = mb(0, "Click OK if you see this!",
                "Windows API call", c)
            Dim s As String = "Windows API MessageBox returned " &
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"
            Return s
        End Function
    End Class
    ```

     È possibile testare la funzione `messageThroughWindows` con il codice seguente.

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > I `UInteger` `ULong` `UShort` `SByte` tipi di dati,, e non fanno parte dell' [indipendenza del linguaggio e dei componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) , pertanto il codice conforme a CLS non può utilizzare un componente che li utilizza.

    > [!IMPORTANT]
    > Effettuando una chiamata a codice non gestito, ad esempio Windows Application Programming Interface (API), il codice viene esposto a potenziali rischi per la sicurezza.

    > [!IMPORTANT]
    > Per chiamare l'API Windows è necessaria l'autorizzazione per il codice non gestito, che può influire sulla sua esecuzione in situazioni di attendibilità parziale. Per ulteriori informazioni, vedere <xref:System.Security.Permissions.SecurityPermission> e [autorizzazioni di accesso al codice](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../language-reference/data-types/index.md)
- [Tipo di dati Integer](../../language-reference/data-types/integer-data-type.md)
- [Tipo di dati UInteger](../../language-reference/data-types/uinteger-data-type.md)
- [Declare Statement](../../language-reference/statements/declare-statement.md)
- [Procedura dettagliata: Chiamata delle API di Windows](walkthrough-calling-windows-apis.md)
