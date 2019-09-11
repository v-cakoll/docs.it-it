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
ms.openlocfilehash: 4228da6efe22091c86de95d846c14f504d51457f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851292"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="b0518-102">CorFlags.exe (strumento di conversione CorFlags)</span><span class="sxs-lookup"><span data-stu-id="b0518-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="b0518-103">Lo strumento di conversione CorFlags consente di configurare la sezione CorFlags dell'intestazione di un'immagine eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="b0518-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="b0518-104">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0518-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b0518-105">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="b0518-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="b0518-106">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b0518-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="b0518-107">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b0518-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0518-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0518-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0518-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0518-109">Parameters</span></span>  
  
|<span data-ttu-id="b0518-110">Parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0518-110">Required parameter</span></span>|<span data-ttu-id="b0518-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0518-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="b0518-112">Nome dell'assembly per il quale configurare CorFlags.</span><span class="sxs-lookup"><span data-stu-id="b0518-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="b0518-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="b0518-113">Option</span></span>|<span data-ttu-id="b0518-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b0518-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b0518-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="b0518-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="b0518-116">Imposta il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="b0518-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="b0518-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="b0518-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="b0518-118">Cancella il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="b0518-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="b0518-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="b0518-119">**/32BITPREF+**</span></span>|<span data-ttu-id="b0518-120">Imposta il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="b0518-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="b0518-121">L'applicazione viene eseguita come processo a 32 bit anche sulle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b0518-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="b0518-122">Impostare questo flag solo su file EXE.</span><span class="sxs-lookup"><span data-stu-id="b0518-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="b0518-123">Se il flag viene impostato su una DLL, la DLL non viene caricata nei processi a 64 bit e viene generata un'eccezione <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="b0518-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="b0518-124">Un file EXE con questo flag può essere caricato in un processo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b0518-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="b0518-125">Novità di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b0518-125">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="b0518-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="b0518-126">**/32BITPREF-**</span></span>|<span data-ttu-id="b0518-127">Cancella il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="b0518-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="b0518-128">Novità di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b0518-128">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="b0518-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="b0518-129">**/?**</span></span>|<span data-ttu-id="b0518-130">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="b0518-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="b0518-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="b0518-131">**/Force**</span></span>|<span data-ttu-id="b0518-132">Forza un aggiornamento anche se l'assembly ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b0518-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="b0518-133">**Importante:**  Se si aggiorna un assembly con nome sicuro, è necessario firmarlo nuovamente prima di eseguirne il codice.</span><span class="sxs-lookup"><span data-stu-id="b0518-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="b0518-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="b0518-134">**/help**</span></span>|<span data-ttu-id="b0518-135">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="b0518-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="b0518-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="b0518-136">**/ILONLY+**</span></span>|<span data-ttu-id="b0518-137">Imposta il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="b0518-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="b0518-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="b0518-138">**/ILONLY-**</span></span>|<span data-ttu-id="b0518-139">Cancella il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="b0518-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="b0518-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="b0518-140">**/nologo**</span></span>|<span data-ttu-id="b0518-141">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0518-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="b0518-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="b0518-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="b0518-143">Ripristina la versione 2.0 dell'intestazione CLR.</span><span class="sxs-lookup"><span data-stu-id="b0518-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="b0518-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="b0518-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="b0518-145">Esegue l'aggiornamento dell'intestazione CLR alla versione 2.5.</span><span class="sxs-lookup"><span data-stu-id="b0518-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="b0518-146">**Nota:**  per l'esecuzione nativa, gli assembly devono avere un'intestazione CLR versione 2.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="b0518-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0518-147">Note</span><span class="sxs-lookup"><span data-stu-id="b0518-147">Remarks</span></span>  
 <span data-ttu-id="b0518-148">Se non viene specificata alcuna opzione, lo strumento di conversione CorFlags visualizza i flag relativi all'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="b0518-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0518-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0518-149">See also</span></span>

- [<span data-ttu-id="b0518-150">Strumenti</span><span class="sxs-lookup"><span data-stu-id="b0518-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="b0518-151">Applicazioni a 64 bit</span><span class="sxs-lookup"><span data-stu-id="b0518-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)
- [<span data-ttu-id="b0518-152">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b0518-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
