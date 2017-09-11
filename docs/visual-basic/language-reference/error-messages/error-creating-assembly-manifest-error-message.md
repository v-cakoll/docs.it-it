---
title: 'Errore durante la creazione di manifesto dell&quot;assembly: &lt;messaggio di errore&gt; | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 12e08feff09e901839c4e282d32a0a4e54e12576
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="5111c-102">Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;</span><span class="sxs-lookup"><span data-stu-id="5111c-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="5111c-103">Il compilatore [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto.</span><span class="sxs-lookup"><span data-stu-id="5111c-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="5111c-104">Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5111c-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="5111c-105">Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="5111c-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="5111c-106">Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata.</span><span class="sxs-lookup"><span data-stu-id="5111c-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="5111c-107">Per ritardare la firma di un assembly, è necessario selezionare il **solo firma ritardata** casella di controllo e fornire un file di chiave valido contenente informazioni sulla chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5111c-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="5111c-108">Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="5111c-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="5111c-109">Per ulteriori informazioni, vedere [procedura: firmare un Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span><span class="sxs-lookup"><span data-stu-id="5111c-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="5111c-110">**ID errore:** BC30140</span><span class="sxs-lookup"><span data-stu-id="5111c-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5111c-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5111c-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="5111c-112">Esaminare il messaggio di errore riportato e vedere l'argomento [Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) per correggere l'errore AL1019 ulteriori spiegazioni e consigli</span><span class="sxs-lookup"><span data-stu-id="5111c-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="5111c-113">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5111c-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5111c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5111c-114">See Also</span></span>  
 <span data-ttu-id="5111c-115">[Procedura: firmare un assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span><span class="sxs-lookup"><span data-stu-id="5111c-115">[How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span></span>  
<span data-ttu-id="5111c-116"> [Pagina Firma, Creazione progetti](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span><span class="sxs-lookup"><span data-stu-id="5111c-116"> [Signing Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span></span>  
<span data-ttu-id="5111c-117"> [Assembly Linker (Al.exe)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="5111c-117"> [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="5111c-118"> [Strumento Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="5111c-118"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="5111c-119"> [Comunicazioni con Microsoft](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="5111c-119"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
