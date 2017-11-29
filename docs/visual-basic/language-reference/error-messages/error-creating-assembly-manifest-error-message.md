---
title: 'Errore durante la creazione di manifesto dell''assembly: &lt;messaggio di errore&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="0972e-102">Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;</span><span class="sxs-lookup"><span data-stu-id="0972e-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="0972e-103">Il compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto.</span><span class="sxs-lookup"><span data-stu-id="0972e-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="0972e-104">Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0972e-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="0972e-105">Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="0972e-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="0972e-106">Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata.</span><span class="sxs-lookup"><span data-stu-id="0972e-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="0972e-107">Per ritardare la firma di un assembly, è necessario selezionare la casella di controllo **Solo firma ritardata** e fornire un file di chiave valido contenente informazioni sulla chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="0972e-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="0972e-108">Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="0972e-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="0972e-109">Per ulteriori informazioni, vedere [procedura: firmare un Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span><span class="sxs-lookup"><span data-stu-id="0972e-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="0972e-110">**ID errore:** BC30140</span><span class="sxs-lookup"><span data-stu-id="0972e-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0972e-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="0972e-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="0972e-112">Esaminare il messaggio di errore tra virgolette e consultare l'argomento [Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) per correggere l'errore AL1019 ulteriori spiegazioni e consigli</span><span class="sxs-lookup"><span data-stu-id="0972e-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="0972e-113">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0972e-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0972e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0972e-114">See Also</span></span>  
 [<span data-ttu-id="0972e-115">Procedura: firmare un assembly (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0972e-115">How to: Sign an Assembly (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [<span data-ttu-id="0972e-116">Pagina Firma, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="0972e-116">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 [<span data-ttu-id="0972e-117">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="0972e-117">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="0972e-118">Lo strumento Al.exe errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="0972e-118">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="0972e-119">Comunicazioni con Microsoft</span><span class="sxs-lookup"><span data-stu-id="0972e-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
