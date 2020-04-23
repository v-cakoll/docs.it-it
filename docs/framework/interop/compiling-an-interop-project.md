---
title: Compilazione di un progetto di interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: 32102910ae674a97e941e1346a1898585f503527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123676"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="e6f99-102">Compilazione di un progetto di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="e6f99-102">Compiling an Interop Project</span></span>

<span data-ttu-id="e6f99-103">I progetti di interoperabilità COM che fanno riferimento a uno o più assembly contenenti tipi COM importati vengono compilati come qualunque altro progetto gestito.</span><span class="sxs-lookup"><span data-stu-id="e6f99-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="e6f99-104">È possibile fare riferimento agli assembly di interoperabilità in un ambiente di sviluppo quale Visual Studio oppure da un compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e6f99-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="e6f99-105">In entrambi i casi, perché la compilazione sia corretta, l'assembly di interoperabilità deve trovarsi nella stessa directory degli altri file di progetto.</span><span class="sxs-lookup"><span data-stu-id="e6f99-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="e6f99-106">Esistono due modi per fare riferimento agli assembly di interoperabilità:</span><span class="sxs-lookup"><span data-stu-id="e6f99-106">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="e6f99-107">Tipi di interoperabilità incorporati: a partire da .NET Framework 4 e Visual Studio 2010, è possibile indicare al compilatore di incorporare le informazioni sui tipi da un assembly di interoperabilità nell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e6f99-107">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="e6f99-108">Questa è la tecnica consigliata.</span><span class="sxs-lookup"><span data-stu-id="e6f99-108">This is the recommended technique.</span></span>

- <span data-ttu-id="e6f99-109">Distribuzione di assembly di interoperabilità: è possibile creare un riferimento standard a un assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="e6f99-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="e6f99-110">In questo caso, l'assembly di interoperabilità deve essere distribuito con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e6f99-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="e6f99-111">Le differenze tra queste due tecniche sono discusse più dettagliatamente in [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e6f99-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="e6f99-112">L'incorporamento dei tipi di interoperabilità con Visual Studio è illustrato in [procedura dettagliata: incorporamento di tipi da assembly gestiti in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e6f99-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="e6f99-113">Per fare riferimento a un assembly di interoperabilità con un compilatore da riga di comando e incorporare le informazioni sui tipi nei file eseguibili, usare l'opzione [-link (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o l'opzione [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) del compilatore e specificare il nome dell'assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="e6f99-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="e6f99-114">Le applicazioni Visual C++ non possono incorporare informazioni sul tipo, ma possono interagire con applicazioni o componenti aggiuntivi in grado di farlo.</span><span class="sxs-lookup"><span data-stu-id="e6f99-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="e6f99-115">Per compilare un'applicazione che includa un assembly di interoperabilità primario quando viene distribuita, usare l'opzione del compilatore **/reference** e specificare il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e6f99-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6f99-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6f99-116">See also</span></span>

- [<span data-ttu-id="e6f99-117">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6f99-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="e6f99-118">Indipendenza del linguaggio e componenti indipendenti dal linguaggio</span><span class="sxs-lookup"><span data-stu-id="e6f99-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="e6f99-119">[Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e6f99-119">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="e6f99-120">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6f99-120">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="e6f99-121">Importazione di una libreria dei tipi come assembly</span><span class="sxs-lookup"><span data-stu-id="e6f99-121">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
