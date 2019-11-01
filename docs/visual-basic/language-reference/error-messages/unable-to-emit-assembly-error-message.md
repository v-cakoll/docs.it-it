---
title: "Impossibile creare l'assembly: <error message>"
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 5776755a57fbc2b0086b1c9b6cfbb2f2b7eb03fa
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197268"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="0ae0a-102">Impossibile creare l'assembly: \<messaggio di errore ></span><span class="sxs-lookup"><span data-stu-id="0ae0a-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="0ae0a-103">Il compilatore Visual Basic chiama assembly linker (*al. exe*, noto anche come ALink) per generare un assembly con un manifesto e il linker segnala un errore nella fase di emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="0ae0a-104">**ID errore:** BC30145</span><span class="sxs-lookup"><span data-stu-id="0ae0a-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0ae0a-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="0ae0a-105">To correct this error</span></span>

1. <span data-ttu-id="0ae0a-106">Esaminare il messaggio di errore tra virgolette e consultare l'argomento [al. exe](../../../framework/tools/al-exe-assembly-linker.md) per ulteriori spiegazioni e consigli.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="0ae0a-107">Provare a firmare l'assembly manualmente, usando al [. exe](../../../framework/tools/al-exe-assembly-linker.md) o [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="0ae0a-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="0ae0a-108">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="0ae0a-109">Per firmare manualmente l'assembly</span><span class="sxs-lookup"><span data-stu-id="0ae0a-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="0ae0a-110">Utilizzare [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)per creare un file di coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="0ae0a-111">Questo file ha un'estensione *SNK* .</span><span class="sxs-lookup"><span data-stu-id="0ae0a-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="0ae0a-112">Eliminare il riferimento COM che genera l'errore dal progetto.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="0ae0a-113">Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="0ae0a-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="0ae0a-114">In Windows 10 immettere **prompt dei comandi** per gli sviluppatori nella casella di ricerca sulla barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="0ae0a-115">Selezionare quindi **prompt dei comandi per gli sviluppatori per VS 2017** dall'elenco risultati.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="0ae0a-116">Passare alla directory in cui si vuole inserire il wrapper dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="0ae0a-117">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0ae0a-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="0ae0a-118">Un esempio del comando effettivo che è possibile immettere è:</span><span class="sxs-lookup"><span data-stu-id="0ae0a-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="0ae0a-119">Se un percorso o un file contiene spazi, utilizzare le virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="0ae0a-120">In Visual Studio aggiungere un riferimento all'assembly .NET al file appena creato.</span><span class="sxs-lookup"><span data-stu-id="0ae0a-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ae0a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ae0a-121">See also</span></span>

- [<span data-ttu-id="0ae0a-122">Al. exe</span><span class="sxs-lookup"><span data-stu-id="0ae0a-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="0ae0a-123">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="0ae0a-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="0ae0a-124">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="0ae0a-124">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- <span data-ttu-id="0ae0a-125">[Talk to Us](/visualstudio/ide/feedback-options) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="0ae0a-125">[Talk to Us](/visualstudio/ide/feedback-options)</span></span>
