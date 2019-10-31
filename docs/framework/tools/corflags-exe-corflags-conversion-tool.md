---
title: CorFlags.exe (strumento di conversione CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129855"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="edb7a-102">CorFlags.exe (strumento di conversione CorFlags)</span><span class="sxs-lookup"><span data-stu-id="edb7a-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="edb7a-103">Lo strumento di conversione CorFlags consente di configurare la sezione CorFlags dell'intestazione di un'immagine eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="edb7a-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="edb7a-104">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="edb7a-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="edb7a-105">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="edb7a-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="edb7a-106">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="edb7a-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="edb7a-107">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="edb7a-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb7a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edb7a-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="edb7a-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="edb7a-109">Parameters</span></span>  
  
|<span data-ttu-id="edb7a-110">Parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="edb7a-110">Required parameter</span></span>|<span data-ttu-id="edb7a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edb7a-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="edb7a-112">Nome dell'assembly per il quale configurare CorFlags.</span><span class="sxs-lookup"><span data-stu-id="edb7a-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="edb7a-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="edb7a-113">Option</span></span>|<span data-ttu-id="edb7a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edb7a-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="edb7a-115">Imposta il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="edb7a-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="edb7a-116">Cancella il flag 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="edb7a-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="edb7a-117">Imposta il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="edb7a-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="edb7a-118">L'applicazione viene eseguita come processo a 32 bit anche sulle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="edb7a-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="edb7a-119">Impostare questo flag solo su file EXE.</span><span class="sxs-lookup"><span data-stu-id="edb7a-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="edb7a-120">Se il flag viene impostato su una DLL, la DLL non viene caricata nei processi a 64 bit e viene generata un'eccezione <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="edb7a-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="edb7a-121">Un file EXE con questo flag può essere caricato in un processo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="edb7a-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="edb7a-122">Novità di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="edb7a-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="edb7a-123">Cancella il flag 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="edb7a-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="edb7a-124">Novità di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="edb7a-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="edb7a-125">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="edb7a-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="edb7a-126">Forza un aggiornamento anche se l'assembly ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="edb7a-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="edb7a-127">**Importante:** se si aggiorna un assembly con nome sicuro è necessario firmarlo nuovamente prima di eseguirne il codice.</span><span class="sxs-lookup"><span data-stu-id="edb7a-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="edb7a-128">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="edb7a-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="edb7a-129">Imposta il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="edb7a-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="edb7a-130">Cancella il flag ILONLY.</span><span class="sxs-lookup"><span data-stu-id="edb7a-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="edb7a-131">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="edb7a-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="edb7a-132">Ripristina la versione 2.0 dell'intestazione CLR.</span><span class="sxs-lookup"><span data-stu-id="edb7a-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="edb7a-133">Esegue l'aggiornamento dell'intestazione CLR alla versione 2.5.</span><span class="sxs-lookup"><span data-stu-id="edb7a-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="edb7a-134">**Nota:** per essere eseguiti a livello nativo, gli assembly devono disporre di un'intestazione CLR versione 2.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="edb7a-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edb7a-135">Note</span><span class="sxs-lookup"><span data-stu-id="edb7a-135">Remarks</span></span>  
 <span data-ttu-id="edb7a-136">Se non viene specificata alcuna opzione, lo strumento di conversione CorFlags visualizza i flag relativi all'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="edb7a-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb7a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edb7a-137">See also</span></span>

- [<span data-ttu-id="edb7a-138">Strumenti</span><span class="sxs-lookup"><span data-stu-id="edb7a-138">Tools</span></span>](index.md)
- [<span data-ttu-id="edb7a-139">Applicazioni a 64 bit</span><span class="sxs-lookup"><span data-stu-id="edb7a-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="edb7a-140">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="edb7a-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
