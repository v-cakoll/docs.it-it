---
title: /delaysign | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
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
ms.openlocfilehash: bcc819e08ca7731d91dc77dc831060bcf00a4425
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="delaysign"></a><span data-ttu-id="2179c-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="2179c-102">/delaysign</span></span>
<span data-ttu-id="2179c-103">Specifica se l'assembly avrà firma completa o parziale.</span><span class="sxs-lookup"><span data-stu-id="2179c-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2179c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2179c-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2179c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2179c-105">Arguments</span></span>  
 <span data-ttu-id="2179c-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2179c-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2179c-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2179c-107">Optional.</span></span> <span data-ttu-id="2179c-108">Usare `/delaysign-` se si desidera che l'assembly abbia firma completa.</span><span class="sxs-lookup"><span data-stu-id="2179c-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="2179c-109">Utilizzare `/delaysign+` se si desidera inserire la chiave pubblica nell'assembly e riserva spazio per l'hash con segno.</span><span class="sxs-lookup"><span data-stu-id="2179c-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="2179c-110">Il valore predefinito è `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="2179c-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2179c-111">Note</span><span class="sxs-lookup"><span data-stu-id="2179c-111">Remarks</span></span>  
 <span data-ttu-id="2179c-112">Il `/delaysign` opzione ha effetto solo se utilizzata con [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="2179c-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="2179c-113">Quando si richiede un assembly con firmato completa, il compilatore genera un hash per il file che contiene il manifesto (i metadati dell'assembly) e tale hash viene firmato con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="2179c-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="2179c-114">La firma digitale risultante viene archiviata nel file contenente il manifesto.</span><span class="sxs-lookup"><span data-stu-id="2179c-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="2179c-115">Quando un assembly è impostata la firma ritardata, il compilatore non calcola e archivia la firma ma riserva spazio nel file in modo che la firma possa essere aggiunta successivamente.</span><span class="sxs-lookup"><span data-stu-id="2179c-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="2179c-116">Ad esempio, il metodo `/delaysign+`, uno sviluppatore di un'organizzazione può distribuire versioni di prova senza segno di un assembly che i tester possono registrare con la global assembly cache e utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2179c-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="2179c-117">Termine del lavoro per l'assembly, la persona responsabile della chiave privata dell'organizzazione può firmare completamente l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2179c-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="2179c-118">Questo contesto protegge chiave privata dell'organizzazione dalla divulgazione, consentendo agli sviluppatori di utilizzare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="2179c-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="2179c-119">Vedere [creazione e uso degli assembly](https://msdn.microsoft.com/library/xwb8f617) per ulteriori informazioni su come firmare un assembly.</span><span class="sxs-lookup"><span data-stu-id="2179c-119">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="2179c-120">Per impostare /delaysign in Visual Studio ambiente di sviluppo integrato</span><span class="sxs-lookup"><span data-stu-id="2179c-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="2179c-121">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="2179c-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2179c-122">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2179c-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="2179c-123">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="2179c-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="2179c-124">Fare clic su di **firma** scheda.</span><span class="sxs-lookup"><span data-stu-id="2179c-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="2179c-125">Impostare il valore di **solo firma ritardata** casella.</span><span class="sxs-lookup"><span data-stu-id="2179c-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2179c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2179c-126">See Also</span></span>  
 <span data-ttu-id="2179c-127">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2179c-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2179c-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="2179c-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="2179c-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span><span class="sxs-lookup"><span data-stu-id="2179c-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span></span>  
<span data-ttu-id="2179c-130"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="2179c-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
