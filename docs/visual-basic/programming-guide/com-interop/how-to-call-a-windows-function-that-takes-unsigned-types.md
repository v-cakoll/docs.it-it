---
title: 'Procedura: Chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)'
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
ms.openlocfilehash: e31bc2f9a0b20ce168004fa3ea2210d39a23761e
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738617"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="8aad1-102">Procedura: Chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aad1-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="8aad1-103">Se si sta utilizzando una classe, modulo o una struttura con membri dei tipi di integer senza segno, è possibile accedere a questi membri con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8aad1-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="8aad1-104">Per chiamare una funzione Windows che accetta un tipo unsigned</span><span class="sxs-lookup"><span data-stu-id="8aad1-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="8aad1-105">Usare un [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) per indicare a Visual Basic la libreria che contiene la funzione, che cos'è il nome di tale libreria, che cos'è la sequenza di chiamata e come convertire le stringhe quando viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="8aad1-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="8aad1-106">Nel `Declare` istruzione, utilizzare `UInteger`, `ULong`, `UShort`, o `Byte` come appropriato per ogni parametro con un tipo senza segno.</span><span class="sxs-lookup"><span data-stu-id="8aad1-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="8aad1-107">Consultare la documentazione per la funzione di Windows che per trovare i nomi e valori delle costanti che usa si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="8aad1-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="8aad1-108">Molte di queste sono definiti nel file winuser. H.</span><span class="sxs-lookup"><span data-stu-id="8aad1-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="8aad1-109">Dichiarare le costanti necessarie nel codice.</span><span class="sxs-lookup"><span data-stu-id="8aad1-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="8aad1-110">Molte Windows costanti sono valori senza segno a 32 bit e devono essere dichiarate `As UInteger`.</span><span class="sxs-lookup"><span data-stu-id="8aad1-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As UInteger`.</span></span>  
  
5.  <span data-ttu-id="8aad1-111">Chiamare la funzione in modo normale.</span><span class="sxs-lookup"><span data-stu-id="8aad1-111">Call the function in the normal way.</span></span> <span data-ttu-id="8aad1-112">L'esempio seguente chiama la funzione Windows `MessageBox`, che accetta un argomento di intero senza segno.</span><span class="sxs-lookup"><span data-stu-id="8aad1-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="8aad1-113">È possibile testare la funzione `messageThroughWindows` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8aad1-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="8aad1-114">Il `UInteger`, `ULong`, `UShort`, e `SByte` tipi di dati non sono in parte il [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), pertanto il codice conforme a CLS non è possibile utilizzare un componente che li Usa.</span><span class="sxs-lookup"><span data-stu-id="8aad1-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8aad1-115">Effettua una chiamata a codice non gestito, ad esempio l'interfaccia di programmazione dell'applicazione di Windows (API), espone il codice a potenziali rischi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8aad1-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8aad1-116">Chiamare l'API di Windows richiede l'autorizzazione di accesso al codice non gestito, che possono influire sull'esecuzione in situazioni di attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="8aad1-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="8aad1-117">Per altre informazioni, vedere <xref:System.Security.Permissions.SecurityPermission> e [le autorizzazioni di accesso di codice](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8aad1-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aad1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aad1-118">See also</span></span>
- [<span data-ttu-id="8aad1-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8aad1-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8aad1-120">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="8aad1-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="8aad1-121">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="8aad1-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [<span data-ttu-id="8aad1-122">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="8aad1-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="8aad1-123">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="8aad1-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
