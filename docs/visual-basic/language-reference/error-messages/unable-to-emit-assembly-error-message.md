---
title: "Impossibile creare l'assembly: <error message>"
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 012284aa42dfa29ad1a5e4ec4a4df5eaacbd4fb7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642283"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="b5222-102">Impossibile creare l'assembly: \<messaggio di errore ></span><span class="sxs-lookup"><span data-stu-id="b5222-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="b5222-103">Il compilatore Visual Basic chiama Assembly Linker (*Al.exe*, noto anche come Alink) per generare un assembly con un manifesto e il linker segnala un errore in fase di emissione della creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b5222-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="b5222-104">**ID errore:** BC30145</span><span class="sxs-lookup"><span data-stu-id="b5222-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b5222-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b5222-105">To correct this error</span></span>

1. <span data-ttu-id="b5222-106">Esaminare il messaggio di errore riportato e vedere l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) per spiegazioni e suggerimenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b5222-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="b5222-107">Provare a firmare l'assembly manualmente, utilizzando il [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o nella [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="b5222-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="b5222-108">Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5222-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="b5222-109">Per firmare manualmente l'assembly</span><span class="sxs-lookup"><span data-stu-id="b5222-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="b5222-110">Usare la [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) per creare un file di coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="b5222-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="b5222-111">Questo file contiene un *snk* estensione.</span><span class="sxs-lookup"><span data-stu-id="b5222-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="b5222-112">Eliminare il riferimento COM che genera l'errore dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b5222-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="b5222-113">Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b5222-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="b5222-114">In Windows 10, immettere **prompt dei comandi sviluppatore** nella casella di ricerca nella barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b5222-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="b5222-115">Quindi, selezionare **prompt dei comandi per gli sviluppatori per VS 2017** dall'elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b5222-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="b5222-116">Passare alla directory nella directory in cui si desidera posizionare il wrapper dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b5222-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="b5222-117">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b5222-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="b5222-118">È un esempio del comando effettivo che è possibile immettere:</span><span class="sxs-lookup"><span data-stu-id="b5222-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="b5222-119">Se un file o il percorso contiene spazi, utilizzare le virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="b5222-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="b5222-120">In Visual Studio, aggiungere un riferimento di Assembly .NET per il file che appena creato.</span><span class="sxs-lookup"><span data-stu-id="b5222-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5222-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5222-121">See also</span></span>

- [<span data-ttu-id="b5222-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="b5222-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="b5222-123">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="b5222-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="b5222-124">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="b5222-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- <span data-ttu-id="b5222-125">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="b5222-125">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
