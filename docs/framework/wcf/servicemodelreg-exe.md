---
title: Strumento di registrazione ServiceModel (ServiceModelReg.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cfe522817fdc9a2aea23b1c9e8dce3b658d892c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="b3572-102">Strumento di registrazione ServiceModel (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="b3572-102">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="b3572-103">Questo strumento da riga di comando offre la possibilità di gestire la registrazione di componenti WCF e WF in un singolo computer.</span><span class="sxs-lookup"><span data-stu-id="b3572-103">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="b3572-104">In condizioni normali l'utilizzo di questo strumento non è consigliabile perché i componenti WCF e WF vengono configurati quando installati.</span><span class="sxs-lookup"><span data-stu-id="b3572-104">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="b3572-105">Tuttavia, se si verificano problemi con l'attivazione del servizio, si può tentare la registrazione dei componenti tramite questo strumento.</span><span class="sxs-lookup"><span data-stu-id="b3572-105">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3572-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3572-106">Syntax</span></span>  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="b3572-107">Note</span><span class="sxs-lookup"><span data-stu-id="b3572-107">Remarks</span></span>  
 <span data-ttu-id="b3572-108">Lo strumento si trova nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="b3572-108">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="b3572-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="b3572-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3572-110">Quando viene eseguito lo strumento di registrazione ServiceModel [!INCLUDE[wv](../../../includes/wv-md.md)], **le funzionalità di Windows** finestra di dialogo potrebbe non indicare il **Attivazione HTTP di Windows Communication Foundation** perl'opzione**Microsoft .NET Framework 3.0** è attivata.</span><span class="sxs-lookup"><span data-stu-id="b3572-110">When the ServiceModel Registration Tool is run on [!INCLUDE[wv](../../../includes/wv-md.md)], the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="b3572-111">Il **le funzionalità di Windows** finestra di dialogo è possibile accedere facendo clic su **avviare**, quindi fare clic su **eseguire** e quindi digitando **OptionalFeatures**.</span><span class="sxs-lookup"><span data-stu-id="b3572-111">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="b3572-112">Nella tabella riportata di seguito sono descritte le opzioni che possono essere utilizzate con ServiceModelReg.exe.</span><span class="sxs-lookup"><span data-stu-id="b3572-112">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="b3572-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="b3572-113">Option</span></span>|<span data-ttu-id="b3572-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3572-114">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="b3572-115">Installa tutti i componenti WCF e WF.</span><span class="sxs-lookup"><span data-stu-id="b3572-115">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="b3572-116">Disinstalla tutti i componenti WCF e WF.</span><span class="sxs-lookup"><span data-stu-id="b3572-116">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="b3572-117">Ripristina tutti i componenti WCF e WF.</span><span class="sxs-lookup"><span data-stu-id="b3572-117">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="b3572-118">Installa tutti i componenti WCF e WF specificati con -c.</span><span class="sxs-lookup"><span data-stu-id="b3572-118">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="b3572-119">Disinstalla tutti i componenti WCF e WF specificati con -c.</span><span class="sxs-lookup"><span data-stu-id="b3572-119">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="b3572-120">Installa o disinstalla un componente:</span><span class="sxs-lookup"><span data-stu-id="b3572-120">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="b3572-121">-httpnamespace-prenotazione Namespace HTTP</span><span class="sxs-lookup"><span data-stu-id="b3572-121">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="b3572-122">porta TCP - tcpportsharing-servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="b3572-122">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="b3572-123">servizio di attivazione - tcpactivation-TCP (non supportato in .NET 4 Client Profile)</span><span class="sxs-lookup"><span data-stu-id="b3572-123">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="b3572-124">-namedpipeactivation-Named pipe activation service (non supportato in .NET 4 Client Profile</span><span class="sxs-lookup"><span data-stu-id="b3572-124">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="b3572-125">servizio di attivazione MSMQ - msmqactivation-(non supportato in .NET 4 Client Profile</span><span class="sxs-lookup"><span data-stu-id="b3572-125">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="b3572-126">ETW - etw-manifesti di traccia eventi (Windows Vista o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="b3572-126">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="b3572-127">Modalità non interattiva (solo registrazione errori visualizzata)</span><span class="sxs-lookup"><span data-stu-id="b3572-127">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="b3572-128">Modalità dettagliata.</span><span class="sxs-lookup"><span data-stu-id="b3572-128">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="b3572-129">Elimina le informazioni di copyright e il messaggio di avvio.</span><span class="sxs-lookup"><span data-stu-id="b3572-129">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="b3572-130">Visualizza il testo della Guida</span><span class="sxs-lookup"><span data-stu-id="b3572-130">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="b3572-131">Correzione dell’errore FileLoadException </span><span class="sxs-lookup"><span data-stu-id="b3572-131">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="b3572-132">Se sono state installate versioni precedenti di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sul computer, è possibile che venga visualizzato un errore `FileLoadFoundException` durante l’esecuzione dello strumento ServiceModelReg per registrare una nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="b3572-132">If you installed previous versions of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="b3572-133">Ciò può verificarsi anche se sono stati rimossi manualmente file dall’installazione precedente, ma sono state mantenute intatte le impostazioni machine.config.</span><span class="sxs-lookup"><span data-stu-id="b3572-133">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="b3572-134">Verrà visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b3572-134">The error message is similar to the following.</span></span>  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="b3572-135">È necessario notare dal messaggio di errore che è stato installato l’assembly System.ServiceModel Versione 2.0.0.0 di una precedente versione di Customer Technology Preview (CTP).</span><span class="sxs-lookup"><span data-stu-id="b3572-135">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="b3572-136">La versione corrente dell'assembly System.ServiceModel rilasciata è invece 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="b3572-136">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="b3572-137">Pertanto, è possibile incontrare questo problema quando si vuole installare la versione ufficiale [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] su un computer nel quale è stata installata una precedente versione di CTP [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], ma non completamente disinstallata.</span><span class="sxs-lookup"><span data-stu-id="b3572-137">Therefore, this issue is encountered when you want to install the official [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] release on a machine where an early CTP release of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="b3572-138">ServiceModelReg.exe non può eseguire la pulizia di voci della versione precedente, né può registrare voci della versione nuova.</span><span class="sxs-lookup"><span data-stu-id="b3572-138">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="b3572-139">L’unica soluzione alternativa è modificare manualmente machine.config. È possibile trovare questo file al percorso seguente.</span><span class="sxs-lookup"><span data-stu-id="b3572-139">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="b3572-140">Se si esegue [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] su un computer a 64 bit, è necessario modificare lo stesso file anche in questa posizione.</span><span class="sxs-lookup"><span data-stu-id="b3572-140">If you are running [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="b3572-141">Individuare tutti i nodi XML nel file che fanno riferimento a "System. ServiceModel, Version = 2.0.0.0", eliminare tali nodi e i nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="b3572-141">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="b3572-142">Per risolvere il problema, salvare il file e ripetere l'esecuzione di ServiceModelReg.exe.</span><span class="sxs-lookup"><span data-stu-id="b3572-142">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b3572-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="b3572-143">Examples</span></span>  
 <span data-ttu-id="b3572-144">Negli esempi seguenti viene illustrato come utilizzare le opzioni più comuni dello strumento ServiceModelReg.exe.</span><span class="sxs-lookup"><span data-stu-id="b3572-144">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
