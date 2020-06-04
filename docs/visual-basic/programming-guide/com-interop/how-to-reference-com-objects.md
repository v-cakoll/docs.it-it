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
ms.openlocfilehash: 2e2cbac6fad5e1686b7383c44619b8c6f5326483
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396804"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="156c0-102">Procedura: fare riferimento a oggetti COM da Visual Basic</span><span class="sxs-lookup"><span data-stu-id="156c0-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="156c0-103">In Visual Basic l'aggiunta di riferimenti a oggetti COM con librerie dei tipi richiede la creazione di un assembly di interoperabilità per la libreria COM.</span><span class="sxs-lookup"><span data-stu-id="156c0-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="156c0-104">I riferimenti ai membri dell'oggetto COM vengono instradati all'assembly di interoperabilità e quindi inoltrati all'oggetto COM effettivo.</span><span class="sxs-lookup"><span data-stu-id="156c0-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="156c0-105">Le risposte dall'oggetto COM vengono instradate all'assembly di interoperabilità e inoltrate all'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="156c0-105">Responses from the COM object are routed to the interop assembly and forwarded to your .NET Framework application.</span></span>  
  
 <span data-ttu-id="156c0-106">È possibile fare riferimento a un oggetto COM senza utilizzare un assembly di interoperabilità incorporando le informazioni sul tipo per l'oggetto COM in un assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="156c0-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="156c0-107">Per incorporare le informazioni sul tipo, impostare la `Embed Interop Types` proprietà su `True` per il riferimento all'oggetto com.</span><span class="sxs-lookup"><span data-stu-id="156c0-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="156c0-108">Se si esegue la compilazione utilizzando il compilatore da riga di comando, utilizzare l' `/link` opzione per fare riferimento alla libreria com.</span><span class="sxs-lookup"><span data-stu-id="156c0-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="156c0-109">Per ulteriori informazioni, vedere [-link (Visual Basic)](../../reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="156c0-109">For more information, see [-link (Visual Basic)](../../reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="156c0-110">Visual Basic crea automaticamente assembly di interoperabilità quando si aggiunge un riferimento a una libreria dei tipi dall'Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="156c0-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="156c0-111">Quando si utilizza la riga di comando, è possibile utilizzare l'utilità Tlbimp per creare manualmente assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="156c0-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="156c0-112">Per aggiungere riferimenti a oggetti COM</span><span class="sxs-lookup"><span data-stu-id="156c0-112">To add references to COM objects</span></span>  
  
1. <span data-ttu-id="156c0-113">Scegliere **Aggiungi riferimento** dal menu **progetto** , quindi fare clic sulla scheda **com** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="156c0-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2. <span data-ttu-id="156c0-114">Consente di selezionare il componente che si desidera utilizzare dall'elenco di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="156c0-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3. <span data-ttu-id="156c0-115">Per semplificare l'accesso all'assembly di interoperabilità, aggiungere un' `Imports` istruzione all'inizio della classe o del modulo in cui si utilizzerà l'oggetto com.</span><span class="sxs-lookup"><span data-stu-id="156c0-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="156c0-116">Ad esempio, nell'esempio di codice seguente viene importato lo spazio dei nomi `INKEDLib` per gli oggetti a cui si fa riferimento nella `Microsoft InkEdit Control 1.0` libreria.</span><span class="sxs-lookup"><span data-stu-id="156c0-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="156c0-117">Per creare un assembly di interoperabilità tramite Tlbimp</span><span class="sxs-lookup"><span data-stu-id="156c0-117">To create an interop assembly using Tlbimp</span></span>  
  
1. <span data-ttu-id="156c0-118">Aggiungere il percorso di Tlbimp al percorso di ricerca, se non è già incluso nel percorso di ricerca e non si è attualmente nella directory in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="156c0-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2. <span data-ttu-id="156c0-119">Chiamare Tlbimp da un prompt dei comandi, fornendo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="156c0-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    - <span data-ttu-id="156c0-120">Nome e percorso della DLL contenente la libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="156c0-120">Name and location of the DLL that contains the type library</span></span>  
  
    - <span data-ttu-id="156c0-121">Nome e percorso dello spazio dei nomi in cui devono essere inserite le informazioni</span><span class="sxs-lookup"><span data-stu-id="156c0-121">Name and location of the namespace where the information should be placed</span></span>  
  
    - <span data-ttu-id="156c0-122">Nome e percorso dell'assembly di interoperabilità di destinazione</span><span class="sxs-lookup"><span data-stu-id="156c0-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="156c0-123">Nel codice seguente ne viene illustrato un esempio:</span><span class="sxs-lookup"><span data-stu-id="156c0-123">The following code provides an example:</span></span>  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="156c0-124">È possibile utilizzare Tlbimp per creare assembly di interoperabilità per le librerie dei tipi, anche per gli oggetti COM non registrati.</span><span class="sxs-lookup"><span data-stu-id="156c0-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="156c0-125">Tuttavia, gli oggetti COM a cui fanno riferimento gli assembly di interoperabilità devono essere registrati correttamente nel computer in cui devono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="156c0-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="156c0-126">È possibile registrare un oggetto COM utilizzando l'utilità Regsvr32 inclusa nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="156c0-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="156c0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="156c0-127">See also</span></span>

- [<span data-ttu-id="156c0-128">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="156c0-128">COM Interop</span></span>](index.md)
- [<span data-ttu-id="156c0-129">Tlbimp. exe (utilità di importazione della libreria di tipi)</span><span class="sxs-lookup"><span data-stu-id="156c0-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="156c0-130">Tlbexp. exe (utilità di esportazione della libreria di tipi)</span><span class="sxs-lookup"><span data-stu-id="156c0-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="156c0-131">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="156c0-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="156c0-132">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="156c0-132">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
- [<span data-ttu-id="156c0-133">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="156c0-133">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
