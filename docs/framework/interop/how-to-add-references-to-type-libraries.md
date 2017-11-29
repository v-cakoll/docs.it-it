---
title: 'Procedura: aggiungere riferimenti alle librerie dei tipi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e5bbc99c3c40b0864a7c1c25cb79a3d7c26e3a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="6a838-102">Procedura: aggiungere riferimenti alle librerie dei tipi</span><span class="sxs-lookup"><span data-stu-id="6a838-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="6a838-103">Quando si aggiunge un riferimento a una libreria dei tipi, Visual Studio genera un assembly di interoperabilità contenente metadati.</span><span class="sxs-lookup"><span data-stu-id="6a838-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="6a838-104">Se è disponibile un assembly di interoperabilità primario, prima della generazione di un nuovo assembly di interoperabilità in Visual Studio verrà utilizzato l'assembly esistente.</span><span class="sxs-lookup"><span data-stu-id="6a838-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="6a838-105">Per aggiungere un riferimento a una libreria dei tipi in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6a838-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="6a838-106">Installare il file COM DLL o EXE nel computer, a meno che non si esegua l'installazione con un file Setup.exe di Windows.</span><span class="sxs-lookup"><span data-stu-id="6a838-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="6a838-107">Scegliere **Progetto**, **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="6a838-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="6a838-108">In Gestione riferimenti scegliere **COM**.</span><span class="sxs-lookup"><span data-stu-id="6a838-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="6a838-109">Selezionare la libreria dei tipi nell'elenco o cercare il file con estensione tlb.</span><span class="sxs-lookup"><span data-stu-id="6a838-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="6a838-110">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a838-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="6a838-111">In Esplora soluzioni aprire il menu di scelta rapida per il riferimento appena aggiunto e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6a838-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="6a838-112">Nella finestra **Proprietà** verificare che la proprietà **Incorpora tipi di interoperabilità** sia impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="6a838-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="6a838-113">In questo modo Visual Studio incorporerà nei file eseguibili le informazioni sui tipi COM, eliminando l'esigenza di distribuire assembly di interoperabilità primari con l'app.</span><span class="sxs-lookup"><span data-stu-id="6a838-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a838-114">Le opzioni del menu e della finestra di dialogo possono variare a seconda della versione di Visual Studio in uso.</span><span class="sxs-lookup"><span data-stu-id="6a838-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="6a838-115">Per aggiungere un riferimento a una libreria dei tipi per la compilazione da riga di comando</span><span class="sxs-lookup"><span data-stu-id="6a838-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="6a838-116">Generare un assembly di interoperabilità, come descritto in [Procedura: Generare assembly di interoperabilità da librerie dei tipi](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="6a838-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="6a838-117">Usare l'opzione del compilatore [/link (opzioni del compilatore C#)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) con il nome dell'assembly di interoperabilità per incorporare informazioni sui tipi COM nei file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="6a838-117">Use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a838-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a838-118">See Also</span></span>  
 [<span data-ttu-id="6a838-119">Importazione di una libreria dei tipi come assembly</span><span class="sxs-lookup"><span data-stu-id="6a838-119">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="6a838-120">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a838-120">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="6a838-121">Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="6a838-121">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="6a838-122">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti</span><span class="sxs-lookup"><span data-stu-id="6a838-122">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="6a838-123">/link (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6a838-123">/link (C# Compiler Options)</span></span>](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="6a838-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a838-124">/link (Visual Basic)</span></span>](~/docs/visual-basic/reference/command-line-compiler/link.md)
