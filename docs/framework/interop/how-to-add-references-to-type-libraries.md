---
title: 'Procedura: Aggiungere riferimenti alle librerie dei tipi'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c12096739e66a47fadd89eb27e30ba3de43c7da3
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836435"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="1268a-102">Procedura: Aggiungere riferimenti alle librerie dei tipi</span><span class="sxs-lookup"><span data-stu-id="1268a-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="1268a-103">Quando si aggiunge un riferimento a una libreria dei tipi, Visual Studio genera un assembly di interoperabilità contenente metadati.</span><span class="sxs-lookup"><span data-stu-id="1268a-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="1268a-104">Se è disponibile un assembly di interoperabilità primario, prima della generazione di un nuovo assembly di interoperabilità in Visual Studio verrà utilizzato l'assembly esistente.</span><span class="sxs-lookup"><span data-stu-id="1268a-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="1268a-105">Per aggiungere un riferimento a una libreria dei tipi in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1268a-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="1268a-106">Installare il file COM DLL o EXE nel computer, a meno che non si esegua l'installazione con un file Setup.exe di Windows.</span><span class="sxs-lookup"><span data-stu-id="1268a-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="1268a-107">Scegliere **Progetto**, **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="1268a-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="1268a-108">In Gestione riferimenti scegliere **COM**.</span><span class="sxs-lookup"><span data-stu-id="1268a-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="1268a-109">Selezionare la libreria dei tipi nell'elenco o cercare il file con estensione tlb.</span><span class="sxs-lookup"><span data-stu-id="1268a-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="1268a-110">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="1268a-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="1268a-111">In Esplora soluzioni aprire il menu di scelta rapida per il riferimento appena aggiunto e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1268a-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="1268a-112">Nella finestra **Proprietà** verificare che la proprietà **Incorpora tipi di interoperabilità** sia impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="1268a-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="1268a-113">In questo modo Visual Studio incorporerà nei file eseguibili le informazioni sui tipi COM, eliminando l'esigenza di distribuire assembly di interoperabilità primari con l'app.</span><span class="sxs-lookup"><span data-stu-id="1268a-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1268a-114">Le opzioni del menu e della finestra di dialogo possono variare a seconda della versione di Visual Studio in uso.</span><span class="sxs-lookup"><span data-stu-id="1268a-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="1268a-115">Per aggiungere un riferimento a una libreria dei tipi per la compilazione da riga di comando</span><span class="sxs-lookup"><span data-stu-id="1268a-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="1268a-116">Generare un assembly di interoperabilità come descritto in [Procedura: Generare assembly di interoperabilità da librerie dei tipi](how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="1268a-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="1268a-117">Usare l'opzione del compilatore [/link (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) con il nome dell'assembly di interoperabilità per incorporare informazioni sui tipi COM nei file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="1268a-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1268a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1268a-118">See also</span></span>
- [<span data-ttu-id="1268a-119">Importazione di una libreria dei tipi come assembly</span><span class="sxs-lookup"><span data-stu-id="1268a-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="1268a-120">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1268a-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="1268a-121">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="1268a-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 
- [<span data-ttu-id="1268a-122">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1268a-122">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="1268a-123">/link (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="1268a-123">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="1268a-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1268a-124">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
