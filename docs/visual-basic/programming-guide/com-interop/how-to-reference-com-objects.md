---
title: 'Procedura: fare riferimento a oggetti COM da Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 293bf76b1520f50e67837942eab2f27a49e330e3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204786"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="b7e1f-102">Procedura: fare riferimento a oggetti COM da Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7e1f-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="b7e1f-103">In Visual Basic, l'aggiunta di riferimenti a oggetti COM con librerie dei tipi richiede la creazione di un assembly di interoperabilità per la libreria COM.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="b7e1f-104">I riferimenti ai membri dell'oggetto COM vengono indirizzati all'assembly di interoperabilità e quindi inoltrati all'oggetto COM effettivo.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="b7e1f-105">Le risposte dall'oggetto COM vengono indirizzate all'assembly di interoperabilità e inoltrate al [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="b7e1f-106">È possibile fare riferimento a un oggetto COM senza usare un assembly di interoperabilità per incorporare le informazioni sul tipo per l'oggetto COM in un assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="b7e1f-107">Per incorporare le informazioni sul tipo, impostare il `Embed Interop Types` proprietà `True` per il riferimento all'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="b7e1f-108">Se esegue la compilazione usando il compilatore della riga di comando, usare il `/link` opzione per fare riferimento alla libreria COM.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="b7e1f-109">Per altre informazioni, vedere [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="b7e1f-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="b7e1f-110">Visual Basic crea automaticamente gli assembly di interoperabilità quando si aggiunge un riferimento a una libreria dei tipi dall'ambiente di sviluppo integrato (IDE).</span><span class="sxs-lookup"><span data-stu-id="b7e1f-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="b7e1f-111">Quando si lavora dalla riga di comando, è possibile utilizzare l'utilità Tlbimp per creare manualmente gli assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="b7e1f-112">Per aggiungere riferimenti agli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="b7e1f-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="b7e1f-113">Nel **progetto** menu, scegliere **Aggiungi riferimento** e quindi fare clic sui **COM** scheda nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="b7e1f-114">Selezionare il componente da usare dall'elenco di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="b7e1f-115">Per semplificare l'accesso all'assembly di interoperabilità, aggiungere un `Imports` istruzione all'inizio della classe o modulo in cui si userà l'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="b7e1f-116">Ad esempio, il codice seguente importa lo spazio dei nomi `INKEDLib` per gli oggetti a cui fa riferimento il `Microsoft InkEdit Control 1.0` libreria.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="b7e1f-117">Per creare un assembly di interoperabilità tramite Tlbimp</span><span class="sxs-lookup"><span data-stu-id="b7e1f-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="b7e1f-118">Aggiungere il percorso di Tlbimp al percorso di ricerca, se non è già parte del percorso di ricerca e non si è attualmente nella directory in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="b7e1f-119">Tlbimp chiamata da un prompt dei comandi, fornendo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7e1f-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="b7e1f-120">Nome e il percorso della DLL che contiene la libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="b7e1f-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="b7e1f-121">Nome e il percorso dello spazio dei nomi in cui devono essere inserite le informazioni</span><span class="sxs-lookup"><span data-stu-id="b7e1f-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="b7e1f-122">Nome e percorso dell'assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="b7e1f-123">Nel codice seguente ne viene illustrato un esempio:</span><span class="sxs-lookup"><span data-stu-id="b7e1f-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="b7e1f-124">È possibile utilizzare Tlbimp per creare assembly di interoperabilità di librerie dei tipi, anche per gli oggetti COM non registrati.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="b7e1f-125">Tuttavia, gli oggetti COM a cui fa riferimento l'assembly di interoperabilità devono essere registrati correttamente nel computer in cui sono utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="b7e1f-126">È possibile registrare un oggetto COM tramite l'utilità Regsvr32 incluso con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="b7e1f-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e1f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7e1f-127">See also</span></span>

- [<span data-ttu-id="b7e1f-128">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="b7e1f-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
- [<span data-ttu-id="b7e1f-129">Tlbimp.exe (utilità di importazione della libreria dei tipi)</span><span class="sxs-lookup"><span data-stu-id="b7e1f-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
- [<span data-ttu-id="b7e1f-130">Tlbexp.exe (utilità di esportazione della libreria dei tipi)</span><span class="sxs-lookup"><span data-stu-id="b7e1f-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)  
- [<span data-ttu-id="b7e1f-131">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="b7e1f-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
- [<span data-ttu-id="b7e1f-132">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b7e1f-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
- [<span data-ttu-id="b7e1f-133">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="b7e1f-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
