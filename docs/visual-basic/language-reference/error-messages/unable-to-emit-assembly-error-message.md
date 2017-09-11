---
title: 'Impossibile creare l&quot;assembly: &lt;messaggio di errore&gt; | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
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
ms.openlocfilehash: d15981a1a2fb31ba377066fa421f5a9979d47a12
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="b777f-102">Impossibile creare l'assembly: &lt;messaggio di errore&gt;</span><span class="sxs-lookup"><span data-stu-id="b777f-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="b777f-103">Il compilatore di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto e il linker segnala un errore nella fase di emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b777f-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="b777f-104">**ID errore:** BC30145</span><span class="sxs-lookup"><span data-stu-id="b777f-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b777f-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b777f-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="b777f-106">Esaminare il messaggio di errore riportato e vedere l'argomento [Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) per ulteriori spiegazioni e consigli.</span><span class="sxs-lookup"><span data-stu-id="b777f-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="b777f-107">Provare a firmare l'assembly manualmente, utilizzando il [Assembly Linker (Al.exe)](https://msdn.microsoft.com/library/c405shex) o [Sn.exe (strumento nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="b777f-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="b777f-108">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b777f-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="b777f-109">Per firmare manualmente l'assembly</span><span class="sxs-lookup"><span data-stu-id="b777f-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="b777f-110">Utilizzare il [Sn.exe (strumento nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23) per creare un file di coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="b777f-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="b777f-111">L'estensione di questo file è .snk.</span><span class="sxs-lookup"><span data-stu-id="b777f-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="b777f-112">Eliminare il riferimento COM che genera l'errore dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b777f-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="b777f-113">Da Windows **avviare** dal menu **programmi**, scegliere **Microsoft Visual Studio 2008**, scegliere **Visual Studio Tools**, quindi fare clic su **Prompt dei comandi di Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="b777f-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="b777f-114">Passare alla directory in cui si desidera posizionare il wrapper dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b777f-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="b777f-115">Digitare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b777f-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="b777f-116">Il codice da digitare potrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="b777f-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="b777f-117">Se contiene spazi, il file o il percorso deve essere racchiuso tra virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="b777f-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="b777f-118">In [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] aggiungere un riferimento assembly .NET al file appena creato.</span><span class="sxs-lookup"><span data-stu-id="b777f-118">In [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b777f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b777f-119">See Also</span></span>  
 <span data-ttu-id="b777f-120">[Assembly Linker (Al.exe)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="b777f-120">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="b777f-121"> [Strumento Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="b777f-121"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="b777f-122"> [Sn.exe (strumento nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="b777f-122"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="b777f-123"> [Procedura: Creare una coppia di chiavi pubblica/privata](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span><span class="sxs-lookup"><span data-stu-id="b777f-123"> [How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span></span>  
<span data-ttu-id="b777f-124"> [Comunicazioni con Microsoft](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="b777f-124"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
