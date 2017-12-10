---
title: 'Procedura: chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5b1a306ba694d4bbfc4719fc728112964b1ce40f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="36f33-102">Procedura: chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36f33-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="36f33-103">Se si utilizza una classe, modulo o una struttura con membri dei tipi di valore integer senza segno, è possibile accedere a questi membri con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36f33-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="36f33-104">Per chiamare una funzione Windows che accetta un tipo senza segno</span><span class="sxs-lookup"><span data-stu-id="36f33-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="36f33-105">Utilizzare un [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) indicare [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] la libreria che contiene la funzione, che cos'è il nome nella libreria, qual è la sequenza di chiamata e come eseguire la conversione di stringhe per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36f33-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="36f33-106">Nel `Declare` istruzione, utilizzare `UInteger`, `ULong`, `UShort`, o `Byte` come appropriato per ogni parametro con un tipo senza segno.</span><span class="sxs-lookup"><span data-stu-id="36f33-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="36f33-107">Consultare la documentazione per la funzione di Windows che si sta chiamando per trovare i nomi e i valori delle costanti utilizzate.</span><span class="sxs-lookup"><span data-stu-id="36f33-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="36f33-108">Molte di queste vengono definite nel file winuser. H.</span><span class="sxs-lookup"><span data-stu-id="36f33-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="36f33-109">Dichiarare le costanti necessarie nel codice.</span><span class="sxs-lookup"><span data-stu-id="36f33-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="36f33-110">Molte costanti Windows sono valori senza segno a 32 bit e devono essere dichiarate `As``UInteger`.</span><span class="sxs-lookup"><span data-stu-id="36f33-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="36f33-111">Chiamare la funzione nel modo normale.</span><span class="sxs-lookup"><span data-stu-id="36f33-111">Call the function in the normal way.</span></span> <span data-ttu-id="36f33-112">Nell'esempio seguente viene chiamata la funzione Windows `MessageBox`, che accetta un argomento di intero senza segno.</span><span class="sxs-lookup"><span data-stu-id="36f33-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
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
  
     <span data-ttu-id="36f33-113">È possibile testare la funzione `messageThroughWindows` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="36f33-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="36f33-114">Il `UInteger`, `ULong`, `UShort`, e `SByte` tipi di dati non sono in parte il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), pertanto il codice conforme a CLS non è possibile utilizzare un componente che li utilizza.</span><span class="sxs-lookup"><span data-stu-id="36f33-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="36f33-115">Effettua una chiamata a codice non gestito, ad esempio l'interfaccia di programmazione dell'applicazione di Windows (API), espone il codice a potenziali rischi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="36f33-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="36f33-116">Chiama l'API di Windows è necessaria l'autorizzazione di codice non gestito, che può influire sulla relativa esecuzione in situazioni di attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="36f33-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="36f33-117">Per ulteriori informazioni, vedere <xref:System.Security.Permissions.SecurityPermission> e [le autorizzazioni di accesso di codice](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span><span class="sxs-lookup"><span data-stu-id="36f33-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f33-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36f33-118">See Also</span></span>  
 [<span data-ttu-id="36f33-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="36f33-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="36f33-120">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="36f33-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="36f33-121">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="36f33-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [<span data-ttu-id="36f33-122">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="36f33-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="36f33-123">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="36f33-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
