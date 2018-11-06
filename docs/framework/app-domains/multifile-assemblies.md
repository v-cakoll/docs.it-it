---
title: Assembly con più file
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f319ef94a5a0f1a5239a2f506386dbc15f0505ef
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846422"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="728f8-102">Assembly con più file</span><span class="sxs-lookup"><span data-stu-id="728f8-102">Multifile Assemblies</span></span>

<span data-ttu-id="728f8-103">È possibile creare assembly con più file usando i compilatori della riga di comando o Visual Studio con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="728f8-103">You can create multifile assemblies using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="728f8-104">Un file all'interno dell'assembly deve contenere il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="728f8-104">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="728f8-105">Un assembly che avvia un'applicazione deve inoltre contenere un punto di ingresso, ad esempio un metodo Main o WinMain.</span><span class="sxs-lookup"><span data-stu-id="728f8-105">An assembly that starts an application must also contain an entry point, such as a Main or WinMain method.</span></span>

<span data-ttu-id="728f8-106">Ad esempio, si supponga di avere un'applicazione contenente due moduli di codice, Client.cs e Stringer.cs.</span><span class="sxs-lookup"><span data-stu-id="728f8-106">For example, suppose you have an application that contains two code modules, Client.cs and Stringer.cs.</span></span> <span data-ttu-id="728f8-107">Stringer.cs crea lo spazio dei nomi `myStringer` a cui fa riferimento il codice in Client.cs.</span><span class="sxs-lookup"><span data-stu-id="728f8-107">Stringer.cs creates the `myStringer` namespace that is referenced by the code in Client.cs.</span></span> <span data-ttu-id="728f8-108">Client.cs contiene il metodo `Main`, che è il punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="728f8-108">Client.cs contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="728f8-109">In questo esempio vengono compilati i due moduli di codice e quindi viene creato un terzo file contenente il manifesto dell'assembly che avvia l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="728f8-109">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="728f8-110">Il manifesto dell'assembly fa riferimento a entrambi i moduli `Client` e `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="728f8-110">The assembly manifest references both the `Client` and `Stringer` modules.</span></span>

> [!NOTE]
> <span data-ttu-id="728f8-111">Negli assembly con più file può essere presente un solo punto di ingresso, anche se l'assembly include più moduli di codice.</span><span class="sxs-lookup"><span data-stu-id="728f8-111">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="728f8-112">La scelta di creare un assembly con più file può essere consigliabile per varie ragioni:</span><span class="sxs-lookup"><span data-stu-id="728f8-112">There are several reasons you might want to create a multifile assembly:</span></span>

-   <span data-ttu-id="728f8-113">Per combinare moduli scritti in linguaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="728f8-113">To combine modules written in different languages.</span></span> <span data-ttu-id="728f8-114">Questo è il motivo più comune per la creazione di un assembly con più file.</span><span class="sxs-lookup"><span data-stu-id="728f8-114">This is the most common reason for creating a multifile assembly.</span></span>

-   <span data-ttu-id="728f8-115">Per ottimizzare il download di un'applicazione inserendo i tipi usati raramente in un modulo che verrà scaricato solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="728f8-115">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="728f8-116">Se si creano applicazioni che verranno scaricate usando il tag `<object>` con Microsoft Internet Explorer, è importante creare assembly con più file.</span><span class="sxs-lookup"><span data-stu-id="728f8-116">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="728f8-117">In questo scenario occorrerà creare un file separato dai moduli di codice che contenga solo il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="728f8-117">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="728f8-118">Internet Explorer scarica prima il manifesto dell'assembly e quindi crea i thread di lavoro per scaricare altri moduli o assembly eventualmente necessari.</span><span class="sxs-lookup"><span data-stu-id="728f8-118">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="728f8-119">Durante il download del file che contiene il manifesto dell'assembly, Internet Explorer non risponde all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="728f8-119">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="728f8-120">Tanto minori saranno le dimensioni del file contenente il manifesto dell'assembly, tanto più breve sarà il tempo in cui Internet Explorer non risponderà.</span><span class="sxs-lookup"><span data-stu-id="728f8-120">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

-   <span data-ttu-id="728f8-121">Per combinare moduli di codice scritti da più sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="728f8-121">To combine code modules written by several developers.</span></span> <span data-ttu-id="728f8-122">Sebbene ogni sviluppatore possa compilare ogni modulo di codice in un assembly, questa operazione può forzare l'esposizione pubblica di alcuni tipi che non sarebbero esposti se tutti i moduli venissero inclusi in un assembly con più file.</span><span class="sxs-lookup"><span data-stu-id="728f8-122">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="728f8-123">Dopo aver creato l'assembly, è possibile firmare il file che contiene il manifesto dell'assembly (e quindi l'assembly) oppure è possibile assegnare un nome sicuro al file (e all'assembly) e inserirlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="728f8-123">Once you create the assembly, you can sign the file that contains the assembly manifest (and hence the assembly), or you can give the file (and the assembly) a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="728f8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="728f8-124">See Also</span></span>

- [<span data-ttu-id="728f8-125">Procedura: Compilare un assembly con più file</span><span class="sxs-lookup"><span data-stu-id="728f8-125">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="728f8-126">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="728f8-126">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)