---
title: 'Procedura: fare riferimento agli oggetti COM da Visual Basic | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f7f1112161d9be995cc80378ad9dd95c522198d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="2e785-102">Procedura: fare riferimento a oggetti COM da Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e785-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="2e785-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], aggiunta di riferimenti a oggetti COM che dispongono di librerie richiede la creazione di un assembly di interoperabilità per la libreria COM.</span><span class="sxs-lookup"><span data-stu-id="2e785-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="2e785-104">Riferimenti ai membri dell'oggetto COM vengono indirizzati all'assembly di interoperabilità e quindi inoltrati all'oggetto COM effettivo.</span><span class="sxs-lookup"><span data-stu-id="2e785-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="2e785-105">Le risposte dall'oggetto COM vengono indirizzate all'assembly di interoperabilità e inoltrate al [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e785-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span>  
  
 <span data-ttu-id="2e785-106">È possibile fare riferimento a un oggetto COM senza utilizzare un assembly di interoperabilità incorporando le informazioni sul tipo per l'oggetto COM in un assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="2e785-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="2e785-107">Per incorporare informazioni sul tipo, impostare il `Embed Interop Types` proprietà `True` per il riferimento all'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="2e785-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="2e785-108">Se esegue la compilazione tramite il compilatore della riga di comando, utilizzare il `/link` opzione per fare riferimento alla libreria COM.</span><span class="sxs-lookup"><span data-stu-id="2e785-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="2e785-109">Per ulteriori informazioni, vedere [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="2e785-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2e785-110">Crea automaticamente gli assembly di interoperabilità quando si aggiunge un riferimento a una libreria dei tipi dall'ambiente di sviluppo integrato (IDE).</span><span class="sxs-lookup"><span data-stu-id="2e785-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="2e785-111">Quando si utilizza dalla riga di comando, è possibile utilizzare l'utilità Tlbimp per creare manualmente gli assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="2e785-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="2e785-112">Per aggiungere riferimenti a oggetti COM</span><span class="sxs-lookup"><span data-stu-id="2e785-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="2e785-113">Nel **progetto** menu, scegliere **Aggiungi riferimento** e quindi fare clic su di **COM** scheda nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2e785-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="2e785-114">Selezionare il componente che si desidera utilizzare dall'elenco di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="2e785-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="2e785-115">Per semplificare l'accesso all'assembly di interoperabilità, aggiungere un `Imports` all'inizio della classe o del modulo in cui verrà utilizzato l'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="2e785-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="2e785-116">Ad esempio, nell'esempio seguente importa lo spazio dei nomi `INKEDLib` per gli oggetti a cui fa riferimento il `Microsoft InkEdit Control 1.0` libreria.</span><span class="sxs-lookup"><span data-stu-id="2e785-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     <span data-ttu-id="2e785-117">[!code-vb[&#40; VbVbalrInterop](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2e785-117">[!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span></span>  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="2e785-118">Per creare un assembly di interoperabilità tramite Tlbimp</span><span class="sxs-lookup"><span data-stu-id="2e785-118">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="2e785-119">Aggiungere il percorso di Tlbimp al percorso di ricerca, se non è già parte del percorso di ricerca e non è attualmente la directory in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="2e785-119">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="2e785-120">Tlbimp chiamata da un prompt dei comandi, fornendo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e785-120">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="2e785-121">Nome e il percorso della DLL che contiene la libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="2e785-121">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="2e785-122">Nome e il percorso dello spazio dei nomi in cui inserire le informazioni</span><span class="sxs-lookup"><span data-stu-id="2e785-122">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="2e785-123">Nome e percorso dell'assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="2e785-123">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="2e785-124">Nel codice seguente ne viene illustrato un esempio:</span><span class="sxs-lookup"><span data-stu-id="2e785-124">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="2e785-125">È possibile utilizzare Tlbimp per creare assembly di interoperabilità per librerie dei tipi, anche per gli oggetti COM non registrati.</span><span class="sxs-lookup"><span data-stu-id="2e785-125">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="2e785-126">Tuttavia, gli oggetti COM a cui fa riferimento l'assembly di interoperabilità devono essere registrati correttamente nel computer in cui essi devono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="2e785-126">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="2e785-127">È possibile registrare un oggetto COM tramite l'utilità Regsvr32 incluso con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="2e785-127">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e785-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e785-128">See Also</span></span>  
 <span data-ttu-id="2e785-129">[Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e785-129">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="2e785-130"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span><span class="sxs-lookup"><span data-stu-id="2e785-130"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span></span>  
<span data-ttu-id="2e785-131"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span><span class="sxs-lookup"><span data-stu-id="2e785-131"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span></span>  
<span data-ttu-id="2e785-132"> [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="2e785-132"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="2e785-133"> [Risoluzione dei problemi di interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span><span class="sxs-lookup"><span data-stu-id="2e785-133"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span></span>  
<span data-ttu-id="2e785-134"> [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="2e785-134"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
