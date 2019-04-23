---
title: "Errore durante la creazione del manifesto dell'assembly: <error message>"
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 0f67b772bab3104c00510954d01b200aadfa9e8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296290"
---
# <a name="error-creating-assembly-manifest-error-message"></a><span data-ttu-id="522b9-102">Errore durante la creazione di manifesto dell'assembly: \<messaggio di errore ></span><span class="sxs-lookup"><span data-stu-id="522b9-102">Error creating assembly manifest: \<error message></span></span>
<span data-ttu-id="522b9-103">Il compilatore Visual Basic chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto.</span><span class="sxs-lookup"><span data-stu-id="522b9-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="522b9-104">Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="522b9-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="522b9-105">Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="522b9-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="522b9-106">Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata.</span><span class="sxs-lookup"><span data-stu-id="522b9-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="522b9-107">Per ritardare la firma di un assembly, è necessario selezionare la casella di controllo **Solo firma ritardata** e fornire un file di chiave valido contenente informazioni sulla chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="522b9-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="522b9-108">Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="522b9-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="522b9-109">Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="522b9-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="522b9-110">**ID errore:** BC30140</span><span class="sxs-lookup"><span data-stu-id="522b9-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="522b9-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="522b9-111">To correct this error</span></span>  
  
1. <span data-ttu-id="522b9-112">Esaminare il messaggio di errore riportato e vedere l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="522b9-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="522b9-113">Per ulteriori errore AL1019 spiegazioni e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="522b9-113">for error AL1019 further explanation and advice</span></span>  
  
2. <span data-ttu-id="522b9-114">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="522b9-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522b9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="522b9-115">See also</span></span>

- [<span data-ttu-id="522b9-116">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="522b9-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [<span data-ttu-id="522b9-117">Pagina Firma, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="522b9-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
- [<span data-ttu-id="522b9-118">Al.exe</span><span class="sxs-lookup"><span data-stu-id="522b9-118">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- <span data-ttu-id="522b9-119">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="522b9-119">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
