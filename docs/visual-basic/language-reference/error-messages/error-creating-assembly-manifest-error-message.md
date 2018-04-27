---
title: "Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4032bbcbf9924eb5aad4e2cb1a6e74df9a472eca
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="a62de-102">Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;</span><span class="sxs-lookup"><span data-stu-id="a62de-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="a62de-103">Il compilatore Visual Basic chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto.</span><span class="sxs-lookup"><span data-stu-id="a62de-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="a62de-104">Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a62de-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="a62de-105">Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="a62de-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="a62de-106">Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata.</span><span class="sxs-lookup"><span data-stu-id="a62de-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="a62de-107">Per ritardare la firma di un assembly, è necessario selezionare la casella di controllo **Solo firma ritardata** e fornire un file di chiave valido contenente informazioni sulla chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="a62de-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="a62de-108">Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="a62de-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="a62de-109">Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="a62de-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="a62de-110">**ID errore:** BC30140</span><span class="sxs-lookup"><span data-stu-id="a62de-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a62de-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a62de-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="a62de-112">Esaminare il messaggio di errore tra virgolette e consultare l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="a62de-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="a62de-113">Per correggere l'errore AL1019 ulteriori spiegazioni e consigli</span><span class="sxs-lookup"><span data-stu-id="a62de-113">for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="a62de-114">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a62de-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62de-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a62de-115">See Also</span></span>  
 [<span data-ttu-id="a62de-116">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="a62de-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="a62de-117">Pagina Firma, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="a62de-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 <span data-ttu-id="a62de-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="a62de-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="a62de-119">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="a62de-119">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
