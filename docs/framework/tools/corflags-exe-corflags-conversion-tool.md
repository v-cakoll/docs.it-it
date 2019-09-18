---
title: CorFlags.exe (strumento di conversione CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b420fb451bf1bb2078a4419a648a1407c39ad178
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71044748"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="e6e7f-102">CorFlags.exe (strumento di conversione CorFlags)</span><span class="sxs-lookup"><span data-stu-id="e6e7f-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="e6e7f-103">Lo strumento di conversione CorFlags consente di configurare la sezione CorFlags dell'intestazione di un'immagine eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="e6e7f-104">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="e6e7f-105">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="e6e7f-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="e6e7f-106">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e6e7f-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="e6e7f-107">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e6e7f-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6e7f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6e7f-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6e7f-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6e7f-109">Parameters</span></span>  
  
|<span data-ttu-id="e6e7f-110">Parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-110">Required parameter</span></span>|<span data-ttu-id="e6e7f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6e7f-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="e6e7f-112">Nome dell'assembly per il quale configurare CorFlags.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="e6e7f-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="e6e7f-113">Option</span></span>|<span data-ttu-id="e6e7f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6e7f-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e6e7f-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="e6e7f-116">Imposta il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="e6e7f-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="e6e7f-118">Cancella il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="e6e7f-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-119">**/32BITPREF+**</span></span>|<span data-ttu-id="e6e7f-120">Imposta il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="e6e7f-121">L'applicazione viene eseguita come processo a 32 bit anche sulle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="e6e7f-122">Impostare questo flag solo su file EXE.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="e6e7f-123">Se il flag viene impostato su una DLL, la DLL non viene caricata nei processi a 64 bit e viene generata un'eccezione <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="e6e7f-124">Un file EXE con questo flag può essere caricato in un processo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="e6e7f-125">Novità di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-125">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="e6e7f-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-126">**/32BITPREF-**</span></span>|<span data-ttu-id="e6e7f-127">Cancella il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="e6e7f-128">Novità di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-128">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="e6e7f-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-129">**/?**</span></span>|<span data-ttu-id="e6e7f-130">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="e6e7f-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-131">**/Force**</span></span>|<span data-ttu-id="e6e7f-132">Forza un aggiornamento anche se l'assembly ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="e6e7f-133">**Importante:**  Se si aggiorna un assembly con nome sicuro, è necessario firmarlo nuovamente prima di eseguirne il codice.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="e6e7f-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-134">**/help**</span></span>|<span data-ttu-id="e6e7f-135">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="e6e7f-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-136">**/ILONLY+**</span></span>|<span data-ttu-id="e6e7f-137">Imposta il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="e6e7f-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-138">**/ILONLY-**</span></span>|<span data-ttu-id="e6e7f-139">Cancella il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="e6e7f-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-140">**/nologo**</span></span>|<span data-ttu-id="e6e7f-141">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="e6e7f-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="e6e7f-143">Ripristina la versione 2.0 dell'intestazione CLR.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="e6e7f-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="e6e7f-145">Esegue l'aggiornamento dell'intestazione CLR alla versione 2.5.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="e6e7f-146">**Nota:**  per l'esecuzione nativa, gli assembly devono avere un'intestazione CLR versione 2.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6e7f-147">Note</span><span class="sxs-lookup"><span data-stu-id="e6e7f-147">Remarks</span></span>  
 <span data-ttu-id="e6e7f-148">Se non viene specificata alcuna opzione, lo strumento di conversione CorFlags visualizza i flag relativi all'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e7f-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6e7f-149">See also</span></span>

- [<span data-ttu-id="e6e7f-150">Strumenti</span><span class="sxs-lookup"><span data-stu-id="e6e7f-150">Tools</span></span>](index.md)
- [<span data-ttu-id="e6e7f-151">Applicazioni a 64 bit</span><span class="sxs-lookup"><span data-stu-id="e6e7f-151">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="e6e7f-152">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="e6e7f-152">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
