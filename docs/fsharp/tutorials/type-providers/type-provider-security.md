---
title: Sicurezza dei provider di tipi
description: 'Informazioni sulla sicurezza dei provider di tipi in F #, incluso come modificare le impostazioni di trust per un provider di tipi.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a><span data-ttu-id="3e52d-104">Sicurezza dei provider di tipi</span><span class="sxs-lookup"><span data-stu-id="3e52d-104">Type Provider Security</span></span>

<span data-ttu-id="3e52d-105">Provider di tipi sono assembly (DLL) a cui fa riferimento il progetto F # o uno script che contengono codice per la connessione alle origini dati esterne e l'area di questo tipo di informazioni per l'ambiente di tipo F #.</span><span class="sxs-lookup"><span data-stu-id="3e52d-105">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="3e52d-106">In genere, codice negli assembly di riferimento viene eseguito solo quando si compila e quindi eseguire il codice (o nel caso di uno script, inviare il codice di F # Interactive).</span><span class="sxs-lookup"><span data-stu-id="3e52d-106">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="3e52d-107">Tuttavia, un assembly di provider di tipo verrà eseguita all'interno di Visual Studio quando il codice è semplicemente visualizzato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="3e52d-107">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="3e52d-108">Ciò accade perché i provider di tipo devono eseguire per aggiungere informazioni aggiuntive per l'editor, ad esempio le descrizioni comandi informazioni rapide, al completamento di IntelliSense e così via.</span><span class="sxs-lookup"><span data-stu-id="3e52d-108">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="3e52d-109">Di conseguenza, esistono considerazioni sulla protezione aggiuntiva per il tipo di assembly del provider, poiché vengono eseguiti automaticamente all'interno del processo di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e52d-109">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>


## <a name="security-warning-dialog"></a><span data-ttu-id="3e52d-110">Avviso di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3e52d-110">Security Warning Dialog</span></span>
<span data-ttu-id="3e52d-111">Quando si utilizza un assembly di provider di tipo specifico per la prima volta, Visual Studio visualizza una finestra di dialogo di sicurezza in cui si segnala che il provider di tipi sta per eseguire.</span><span class="sxs-lookup"><span data-stu-id="3e52d-111">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="3e52d-112">Prima di Visual Studio carica il provider di tipi, offre la possibilità di decidere se si considera attendibile questo provider.</span><span class="sxs-lookup"><span data-stu-id="3e52d-112">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="3e52d-113">Se si ritiene attendibile l'origine del provider di tipi, quindi selezionare "Fiducia questo provider di tipi".</span><span class="sxs-lookup"><span data-stu-id="3e52d-113">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="3e52d-114">Se si ritiene attendibile l'origine del provider di tipi, quindi selezionare "Non attendibile questo provider di tipi."</span><span class="sxs-lookup"><span data-stu-id="3e52d-114">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="3e52d-115">Considerare attendibile il provider consente di eseguire in Visual Studio e fornire IntelliSense e compilare funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3e52d-115">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="3e52d-116">Tuttavia, se il provider di tipo stesso è dannoso, in esecuzione il codice potrebbe compromettere il computer.</span><span class="sxs-lookup"><span data-stu-id="3e52d-116">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="3e52d-117">Se il progetto contiene codice che fa riferimento a provider di tipi che si è scelto nella finestra di dialogo non considerare attendibile, quindi in fase di compilazione, il compilatore segnalerà un errore che indica che il provider di tipi non è attendibile.</span><span class="sxs-lookup"><span data-stu-id="3e52d-117">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="3e52d-118">Tutti i tipi che dipendono dal provider di tipi non attendibili sono indicati da sottolineature rosse.</span><span class="sxs-lookup"><span data-stu-id="3e52d-118">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="3e52d-119">È consigliabile esaminare il codice nell'editor.</span><span class="sxs-lookup"><span data-stu-id="3e52d-119">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="3e52d-120">Se si decide di modificare l'impostazione di attendibilità direttamente in Visual Studio, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="3e52d-120">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>


#### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="3e52d-121">Per modificare le impostazioni di trust per i provider di tipi</span><span class="sxs-lookup"><span data-stu-id="3e52d-121">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="3e52d-122">Nel `Tools` dal menu `Options`, espandere il `F# Tools` nodo.</span><span class="sxs-lookup"><span data-stu-id="3e52d-122">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>
<br />

2. <span data-ttu-id="3e52d-123">Selezionare `Type Providers`, nell'elenco di provider di tipi, selezionare la casella di controllo per i provider di tipi è attendibile e deselezionare la casella di controllo per quelli non attendibili.</span><span class="sxs-lookup"><span data-stu-id="3e52d-123">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="3e52d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e52d-124">See Also</span></span>
[<span data-ttu-id="3e52d-125">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="3e52d-125">Type Providers</span></span>](index.md)
