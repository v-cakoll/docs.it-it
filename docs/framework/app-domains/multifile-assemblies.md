---
title: Assembly su più file
description: Usare gli assembly su più file destinati a .NET con i compilatori della riga di comando o Visual Studio con Visual C++. Un file nell'assembly deve conservare il manifesto dell'assembly.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: a5fb41b3b136a325e6b8658da521cba3176e929f
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104631"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="92b6d-104">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="92b6d-104">Multifile assemblies</span></span>

<span data-ttu-id="92b6d-105">È possibile creare assembly su più file destinati ai .NET Framework usando compilatori della riga di comando o Visual Studio con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="92b6d-105">You can create multifile assemblies that target the .NET Framework using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="92b6d-106">Un file all'interno dell'assembly deve contenere il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="92b6d-106">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="92b6d-107">Un assembly che avvia un'applicazione deve contenere anche un punto di ingresso, ad esempio `Main` un `WinMain` metodo o.</span><span class="sxs-lookup"><span data-stu-id="92b6d-107">An assembly that starts an application must also contain an entry point, such as a `Main` or `WinMain` method.</span></span>

<span data-ttu-id="92b6d-108">Si supponga, ad esempio, di disporre di un'applicazione che contiene due moduli di codice, *client.cs* e *Stringer.cs*.</span><span class="sxs-lookup"><span data-stu-id="92b6d-108">For example, suppose you have an application that contains two code modules, *Client.cs* and *Stringer.cs*.</span></span> <span data-ttu-id="92b6d-109">*Stringer.cs* crea lo `myStringer` spazio dei nomi a cui fa riferimento il codice in *client.cs*.</span><span class="sxs-lookup"><span data-stu-id="92b6d-109">*Stringer.cs* creates the `myStringer` namespace that is referenced by the code in *Client.cs*.</span></span> <span data-ttu-id="92b6d-110">*Client.cs* contiene il `Main` metodo, che è il punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92b6d-110">*Client.cs* contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="92b6d-111">In questo esempio vengono compilati i due moduli di codice e quindi viene creato un terzo file contenente il manifesto dell'assembly che avvia l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92b6d-111">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="92b6d-112">Il manifesto dell'assembly fa riferimento ai moduli *client* e *Stringer* .</span><span class="sxs-lookup"><span data-stu-id="92b6d-112">The assembly manifest references both the *Client* and *Stringer* modules.</span></span>

> [!NOTE]
> <span data-ttu-id="92b6d-113">Negli assembly su più file può essere presente un solo punto di ingresso, anche se l'assembly include più moduli di codice.</span><span class="sxs-lookup"><span data-stu-id="92b6d-113">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="92b6d-114">La scelta di creare un assembly su più file può essere consigliabile per varie ragioni:</span><span class="sxs-lookup"><span data-stu-id="92b6d-114">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="92b6d-115">Per combinare moduli scritti in linguaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="92b6d-115">To combine modules written in different languages.</span></span> <span data-ttu-id="92b6d-116">Questo è il motivo più comune per la creazione di un assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="92b6d-116">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="92b6d-117">Per ottimizzare il download di un'applicazione inserendo i tipi usati raramente in un modulo che verrà scaricato solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="92b6d-117">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92b6d-118">Se si creano applicazioni che verranno scaricate usando il tag `<object>` con Microsoft Internet Explorer, è importante creare assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="92b6d-118">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="92b6d-119">In questo scenario occorrerà creare un file separato dai moduli di codice che contenga solo il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="92b6d-119">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="92b6d-120">Internet Explorer scarica prima il manifesto dell'assembly e quindi crea i thread di lavoro per scaricare altri moduli o assembly eventualmente necessari.</span><span class="sxs-lookup"><span data-stu-id="92b6d-120">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="92b6d-121">Durante il download del file che contiene il manifesto dell'assembly, Internet Explorer non risponde all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="92b6d-121">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="92b6d-122">Tanto minori saranno le dimensioni del file contenente il manifesto dell'assembly, tanto più breve sarà il tempo in cui Internet Explorer non risponderà.</span><span class="sxs-lookup"><span data-stu-id="92b6d-122">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="92b6d-123">Per combinare moduli di codice scritti da più sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="92b6d-123">To combine code modules written by several developers.</span></span> <span data-ttu-id="92b6d-124">Sebbene ogni sviluppatore possa compilare ogni modulo di codice in un assembly, questa operazione può forzare l'esposizione pubblica di alcuni tipi che non sarebbero esposti se tutti i moduli venissero inclusi in un assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="92b6d-124">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="92b6d-125">Una volta creato l'assembly, è possibile firmare il file contenente il manifesto dell'assembly e, di conseguenza, l'assembly, oppure è possibile assegnare un nome sicuro al file e all'assembly e inserirlo nell'Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="92b6d-125">Once you create the assembly, you can sign the file that contains the assembly manifest, and hence the assembly, or you can give the file and the assembly a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="92b6d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92b6d-126">See also</span></span>

- [<span data-ttu-id="92b6d-127">Procedura: Creare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="92b6d-127">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="92b6d-128">Programmare con gli assembly</span><span class="sxs-lookup"><span data-stu-id="92b6d-128">Program with assemblies</span></span>](../../standard/assembly/index.md)
