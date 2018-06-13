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
ms.openlocfilehash: d4a5b6d490387f2da441ad95bdf369f700cf2e9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400029"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="44034-102">CorFlags.exe (strumento di conversione CorFlags)</span><span class="sxs-lookup"><span data-stu-id="44034-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="44034-103">Lo strumento di conversione CorFlags consente di configurare la sezione CorFlags dell'intestazione di un'immagine eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="44034-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="44034-104">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="44034-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="44034-105">Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="44034-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="44034-106">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="44034-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="44034-107">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="44034-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44034-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44034-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44034-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="44034-109">Parameters</span></span>  
  
|<span data-ttu-id="44034-110">Parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="44034-110">Required parameter</span></span>|<span data-ttu-id="44034-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44034-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="44034-112">Nome dell'assembly per il quale configurare CorFlags.</span><span class="sxs-lookup"><span data-stu-id="44034-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="44034-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="44034-113">Option</span></span>|<span data-ttu-id="44034-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44034-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="44034-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="44034-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="44034-116">Imposta il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="44034-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="44034-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="44034-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="44034-118">Cancella il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="44034-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="44034-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="44034-119">**/32BITPREF+**</span></span>|<span data-ttu-id="44034-120">Imposta il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="44034-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="44034-121">L'applicazione viene eseguita come processo a 32 bit anche sulle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="44034-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="44034-122">Impostare questo flag solo su file EXE.</span><span class="sxs-lookup"><span data-stu-id="44034-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="44034-123">Se il flag viene impostato su una DLL, la DLL non viene caricata nei processi a 64 bit e viene generata un'eccezione <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="44034-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="44034-124">Un file EXE con questo flag può essere caricato in un processo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="44034-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="44034-125">Nuovo in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44034-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="44034-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="44034-126">**/32BITPREF-**</span></span>|<span data-ttu-id="44034-127">Cancella il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="44034-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="44034-128">Nuovo in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44034-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="44034-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="44034-129">**/?**</span></span>|<span data-ttu-id="44034-130">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="44034-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="44034-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="44034-131">**/Force**</span></span>|<span data-ttu-id="44034-132">Forza un aggiornamento anche se l'assembly ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="44034-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="44034-133">**Importante:** se si aggiorna un assembly con nome sicuro è necessario firmarlo nuovamente prima di eseguirne il codice.</span><span class="sxs-lookup"><span data-stu-id="44034-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="44034-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="44034-134">**/help**</span></span>|<span data-ttu-id="44034-135">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="44034-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="44034-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="44034-136">**/ILONLY+**</span></span>|<span data-ttu-id="44034-137">Imposta il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="44034-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="44034-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="44034-138">**/ILONLY-**</span></span>|<span data-ttu-id="44034-139">Cancella il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="44034-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="44034-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="44034-140">**/nologo**</span></span>|<span data-ttu-id="44034-141">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44034-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="44034-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="44034-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="44034-143">Ripristina la versione 2.0 dell'intestazione CLR.</span><span class="sxs-lookup"><span data-stu-id="44034-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="44034-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="44034-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="44034-145">Esegue l'aggiornamento dell'intestazione CLR alla versione 2.5.</span><span class="sxs-lookup"><span data-stu-id="44034-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="44034-146">**Nota:** per essere eseguiti a livello nativo, gli assembly devono disporre di un'intestazione CLR versione 2.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="44034-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44034-147">Note</span><span class="sxs-lookup"><span data-stu-id="44034-147">Remarks</span></span>  
 <span data-ttu-id="44034-148">Se non viene specificata alcuna opzione, lo strumento di conversione CorFlags visualizza i flag relativi all'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="44034-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44034-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44034-149">See Also</span></span>  
 [<span data-ttu-id="44034-150">Strumenti</span><span class="sxs-lookup"><span data-stu-id="44034-150">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="44034-151">Applicazioni a 64 bit</span><span class="sxs-lookup"><span data-stu-id="44034-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)  
 [<span data-ttu-id="44034-152">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="44034-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
