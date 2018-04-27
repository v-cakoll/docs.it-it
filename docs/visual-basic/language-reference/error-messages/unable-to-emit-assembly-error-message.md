---
title: "Impossibile creare l'assembly: &lt;messaggio di errore&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61a5c6b753b8aa70905027bc1449739769cd8da5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="2c302-102">Impossibile creare l'assembly: &lt;messaggio di errore&gt;</span><span class="sxs-lookup"><span data-stu-id="2c302-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="2c302-103">Il compilatore Visual Basic chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto e il linker segnala un errore in fase di emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2c302-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="2c302-104">**ID errore:** BC30145</span><span class="sxs-lookup"><span data-stu-id="2c302-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c302-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2c302-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="2c302-106">Esaminare il messaggio di errore tra virgolette e consultare l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="2c302-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="2c302-107">Per spiegazioni e suggerimenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="2c302-107">for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="2c302-108">Tenta di firmare l'assembly manualmente, utilizzando il [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o [Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2c302-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
3.  <span data-ttu-id="2c302-109">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c302-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="2c302-110">Per firmare manualmente l'assembly</span><span class="sxs-lookup"><span data-stu-id="2c302-110">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="2c302-111">Usare il [Sn.exe (strumento nome sicuro)][Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)) per creare un file di coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="2c302-111">Use the [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="2c302-112">L'estensione di questo file è .snk.</span><span class="sxs-lookup"><span data-stu-id="2c302-112">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="2c302-113">Eliminare il riferimento COM che genera l'errore dal progetto.</span><span class="sxs-lookup"><span data-stu-id="2c302-113">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="2c302-114">Da Windows **avviare** dal menu **programmi**, scegliere **Microsoft Visual Studio 2008**, scegliere **Visual Studio Tools**, e quindi fare clic su **Prompt dei comandi di Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="2c302-114">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="2c302-115">Passare alla directory in cui si desidera posizionare il wrapper dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2c302-115">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="2c302-116">Digitare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2c302-116">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="2c302-117">Il codice da digitare potrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2c302-117">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="2c302-118">Se contiene spazi, il file o il percorso deve essere racchiuso tra virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="2c302-118">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="2c302-119">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] aggiungere un riferimento assembly .NET al file appena creato.</span><span class="sxs-lookup"><span data-stu-id="2c302-119">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c302-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c302-120">See Also</span></span>  
 
 <span data-ttu-id="2c302-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="2c302-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="2c302-122">[Sn.exe (strumento nome sicuro)] [Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="2c302-122">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="2c302-123">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="2c302-123">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 <span data-ttu-id="2c302-124">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="2c302-124">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
