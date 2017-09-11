---
title: Certmgr.exe (strumento di gestione certificati)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd5d1011a8f8aeadfc7729c3a4f6f56a033110a9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="c9db0-102">Certmgr.exe (strumento di gestione certificati)</span><span class="sxs-lookup"><span data-stu-id="c9db0-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="c9db0-103">Lo strumento di gestione certificati (Certmgr.exe) gestisce certificati, elenchi di scopi consentiti ai certificati ed elenchi di revoche di certificati (CRL, Certificate Revocation List).</span><span class="sxs-lookup"><span data-stu-id="c9db0-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="c9db0-104">Lo strumento viene installato automaticamente insieme a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9db0-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c9db0-105">Per avviare lo strumento, utilizzare il [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c9db0-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9db0-106">Lo strumento di gestione dei certificati (Certmgr.exe) è un'utilità da riga di comando, da non confondere con lo snap-in certificati (Certmgr.msc) di Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="c9db0-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="c9db0-107">Poiché Certmgr.msc in genere si trova nella directory di sistema di Windows, l'immissione di `certmgr` nella riga di comando potrebbe caricare lo snap-in anche se è stato aperto il prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9db0-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Visual Studio Command Prompt.</span></span> <span data-ttu-id="c9db0-108">Questo accade perché il percorso dello snap-in precede il percorso dello strumento di gestione dei certificati nella variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="c9db0-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="c9db0-109">Se si verifica questo problema, è possibile eseguire i comandi Certmgr.exe specificando il percorso dell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c9db0-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="c9db0-110">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9db0-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c9db0-111">Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c9db0-111">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="c9db0-112">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c9db0-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="c9db0-113">Per una panoramica dei certificati X.509, vedere [Utilizzo dei certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c9db0-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="c9db0-114">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c9db0-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9db0-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9db0-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9db0-116">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9db0-116">Parameters</span></span>  
  
|<span data-ttu-id="c9db0-117">Argomento</span><span class="sxs-lookup"><span data-stu-id="c9db0-117">Argument</span></span>|<span data-ttu-id="c9db0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9db0-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c9db0-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="c9db0-119">*sourceStorename*</span></span>|<span data-ttu-id="c9db0-120">Archivio certificati contenente certificati, elenchi di scopi consentiti ai certificati o CRL da aggiungere, eliminare, salvare o visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c9db0-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="c9db0-121">Può trattarsi di un file di archivio o di un archivio di sistema.</span><span class="sxs-lookup"><span data-stu-id="c9db0-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="c9db0-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="c9db0-122">*destinationStorename*</span></span>|<span data-ttu-id="c9db0-123">File o archivio certificati di output.</span><span class="sxs-lookup"><span data-stu-id="c9db0-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="c9db0-124">Opzione</span><span class="sxs-lookup"><span data-stu-id="c9db0-124">Option</span></span>|<span data-ttu-id="c9db0-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9db0-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c9db0-126">**/add**</span><span class="sxs-lookup"><span data-stu-id="c9db0-126">**/add**</span></span>|<span data-ttu-id="c9db0-127">Aggiunge certificati, elenchi di scopi consentiti ai certificati e CRL a un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="c9db0-128">**/all**</span><span class="sxs-lookup"><span data-stu-id="c9db0-128">**/all**</span></span>|<span data-ttu-id="c9db0-129">Aggiunge tutte le voci se usata con **/add**,</span><span class="sxs-lookup"><span data-stu-id="c9db0-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="c9db0-130">le elimina se usata con **/del**</span><span class="sxs-lookup"><span data-stu-id="c9db0-130">Deletes all entries when used with **/del**.</span></span> <span data-ttu-id="c9db0-131">e le visualizza se usata senza le opzioni **/add** o **/del**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-131">Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="c9db0-132">Non è possibile usare l'opzione **/all** con **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-132">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="c9db0-133">**/c**</span><span class="sxs-lookup"><span data-stu-id="c9db0-133">**/c**</span></span>|<span data-ttu-id="c9db0-134">Aggiunge i certificati se usata con **/add**,</span><span class="sxs-lookup"><span data-stu-id="c9db0-134">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="c9db0-135">li elimina se usata con **/del**</span><span class="sxs-lookup"><span data-stu-id="c9db0-135">Deletes certificates when used with **/del**.</span></span> <span data-ttu-id="c9db0-136">e li salva se usata con **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-136">Saves certificates when used with **/put**.</span></span> <span data-ttu-id="c9db0-137">Visualizza certificati quando usata senza le opzioni **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-137">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="c9db0-138">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="c9db0-138">**/CRL**</span></span>|<span data-ttu-id="c9db0-139">Aggiunge i CRL se usata con **/add**,</span><span class="sxs-lookup"><span data-stu-id="c9db0-139">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="c9db0-140">li elimina se usata con **/del**</span><span class="sxs-lookup"><span data-stu-id="c9db0-140">Deletes CRLs when used with **/del**.</span></span> <span data-ttu-id="c9db0-141">e li salva se usata con **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-141">Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="c9db0-142">Visualizza CRL quando usata senza le opzioni **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-142">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="c9db0-143">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="c9db0-143">**/CTL**</span></span>|<span data-ttu-id="c9db0-144">Aggiunge gli elenchi di scopi consentiti se usata con **/add**,</span><span class="sxs-lookup"><span data-stu-id="c9db0-144">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="c9db0-145">li elimina se usata con **/del**</span><span class="sxs-lookup"><span data-stu-id="c9db0-145">Deletes CTLs when used with **/del**.</span></span> <span data-ttu-id="c9db0-146">e li salva se usata con **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-146">Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="c9db0-147">Visualizza gli elenchi di scopi consentiti quando usata senza le opzioni **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-147">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="c9db0-148">**/del**</span><span class="sxs-lookup"><span data-stu-id="c9db0-148">**/del**</span></span>|<span data-ttu-id="c9db0-149">Elimina certificati, elenchi di scopi consentiti e CRL da un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-149">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="c9db0-150">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="c9db0-150">**/e** *encodingType*</span></span>|<span data-ttu-id="c9db0-151">Specifica il tipo di codifica dei certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-151">Specifies the certificate encoding type.</span></span> <span data-ttu-id="c9db0-152">Il valore predefinito è `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-152">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="c9db0-153">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="c9db0-153">**/f** *dwFlags*</span></span>|<span data-ttu-id="c9db0-154">Specifica il flag di archivio aperto.</span><span class="sxs-lookup"><span data-stu-id="c9db0-154">Specifies the store open flag.</span></span> <span data-ttu-id="c9db0-155">Si tratta del parametro *dwFlags* passato a **CertOpenStore**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-155">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="c9db0-156">Il valore predefinito è CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="c9db0-156">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="c9db0-157">Questa opzione viene considerata solo se viene usata l'opzione **/y**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-157">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="c9db0-158">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="c9db0-158">**/h**[**elp**]</span></span>|<span data-ttu-id="c9db0-159">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="c9db0-159">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="c9db0-160">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="c9db0-160">**/n** *nam*</span></span>|<span data-ttu-id="c9db0-161">Specifica il nome comune del certificato da aggiungere, eliminare o salvare.</span><span class="sxs-lookup"><span data-stu-id="c9db0-161">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="c9db0-162">È possibile usare questa opzione solo con certificati, non con elenchi di scopi consentiti o CRL.</span><span class="sxs-lookup"><span data-stu-id="c9db0-162">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="c9db0-163">**/put**</span><span class="sxs-lookup"><span data-stu-id="c9db0-163">**/put**</span></span>|<span data-ttu-id="c9db0-164">Salva su file un certificato X.509, un elenco di scopi consentiti o un CRL da un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-164">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="c9db0-165">Il file viene salvato nel formato X.509.</span><span class="sxs-lookup"><span data-stu-id="c9db0-165">The file is saved in X.509 format.</span></span> <span data-ttu-id="c9db0-166">È possibile usare l'opzione **/7** con l'opzione **/put** per salvare il file nel formato PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="c9db0-166">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="c9db0-167">L'opzione **/put** deve essere seguita da **/c**, **/CTL** o **/CRL**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-167">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="c9db0-168">Non è possibile usare l'opzione **/all** con **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-168">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="c9db0-169">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="c9db0-169">**/r** *location*</span></span>|<span data-ttu-id="c9db0-170">Identifica la posizione dell'archivio di sistema all'interno del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="c9db0-170">Identifies the registry location of the system store.</span></span> <span data-ttu-id="c9db0-171">Questa opzione viene considerata solo se viene specificata l'opzione **/s**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-171">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="c9db0-172">*location* deve essere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9db0-172">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="c9db0-173">-   `currentUser` indica che l'archivio certificati si trova sotto la chiave HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="c9db0-173">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="c9db0-174">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c9db0-174">This is the default.</span></span><br /><span data-ttu-id="c9db0-175">-   `localMachine` indica che l'archivio certificati si trova sotto la chiave HKEY_LOCAL_MACHINE.</span><span class="sxs-lookup"><span data-stu-id="c9db0-175">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="c9db0-176">**/s**</span><span class="sxs-lookup"><span data-stu-id="c9db0-176">**/s**</span></span>|<span data-ttu-id="c9db0-177">Indica che l'archivio certificati è un archivio di sistema.</span><span class="sxs-lookup"><span data-stu-id="c9db0-177">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="c9db0-178">Se non si specifica questa opzione, l'archivio viene considerato come **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-178">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="c9db0-179">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="c9db0-179">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="c9db0-180">Specifica l'hash SHA1 del certificato, dell'elenco di scopi consentiti o del CRL da aggiungere, eliminare o salvare.</span><span class="sxs-lookup"><span data-stu-id="c9db0-180">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="c9db0-181">**/v**</span><span class="sxs-lookup"><span data-stu-id="c9db0-181">**/v**</span></span>|<span data-ttu-id="c9db0-182">Specifica la modalità dettagliata. Visualizza informazioni dettagliate su certificati, elenchi di scopi consentiti e CRL.</span><span class="sxs-lookup"><span data-stu-id="c9db0-182">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="c9db0-183">Non è possibile usare questa opzione con le opzioni **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="c9db0-183">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="c9db0-184">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="c9db0-184">**/y** *provider*</span></span>|<span data-ttu-id="c9db0-185">Specifica il nome del provider dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="c9db0-185">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="c9db0-186">**/7**</span><span class="sxs-lookup"><span data-stu-id="c9db0-186">**/7**</span></span>|<span data-ttu-id="c9db0-187">Salva l'archivio di destinazione come oggetto PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="c9db0-187">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="c9db0-188">**/?**</span><span class="sxs-lookup"><span data-stu-id="c9db0-188">**/?**</span></span>|<span data-ttu-id="c9db0-189">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="c9db0-189">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9db0-190">Note</span><span class="sxs-lookup"><span data-stu-id="c9db0-190">Remarks</span></span>  
 <span data-ttu-id="c9db0-191">Certmgr.exe svolge le seguenti funzioni di base:</span><span class="sxs-lookup"><span data-stu-id="c9db0-191">Certmgr.exe performs the following basic functions:</span></span>  
  
-   <span data-ttu-id="c9db0-192">Visualizza certificati, elenchi di scopi consentiti e CRL sulla console.</span><span class="sxs-lookup"><span data-stu-id="c9db0-192">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
-   <span data-ttu-id="c9db0-193">Aggiunge certificati, elenchi di scopi consentiti ai certificati e CRL a un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-193">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
-   <span data-ttu-id="c9db0-194">Elimina certificati, elenchi di scopi consentiti e CRL da un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-194">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
-   <span data-ttu-id="c9db0-195">Salva su file un certificato X.509, un elenco di scopi consentiti o un CRL da un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-195">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="c9db0-196">Certmgr.exe funziona con due tipi di archivi certificati: **StoreFile** e archivi di sistema.</span><span class="sxs-lookup"><span data-stu-id="c9db0-196">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="c9db0-197">Non è necessario specificare il tipo di archivio certificati: Certmgr.exe è infatti in grado di identificare il tipo di archivio e di eseguire le operazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="c9db0-197">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="c9db0-198">Se Certmgr.exe viene eseguito senza specificare alcuna opzione, verrà avviato lo snap-in certmgr.msc, che comprende una GUI che assisterà l'utente nell'esecuzione delle attività di gestione dei certificati disponibili anche dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c9db0-198">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="c9db0-199">La GUI fornisce una procedura guidata di importazione che consente di copiare certificati, elenchi di scopi consentiti e CRL dal disco a un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="c9db0-199">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="c9db0-200">È possibile trovare i nomi degli archivi X509Certificate per i parametri `sourceStorename` e `destinationStorename` compilando ed eseguendo il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c9db0-200">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 <span data-ttu-id="c9db0-201">[!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)] [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="c9db0-201">[!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)] [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]</span></span>  
  
 <span data-ttu-id="c9db0-202">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c9db0-202">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c9db0-203">Esempi</span><span class="sxs-lookup"><span data-stu-id="c9db0-203">Examples</span></span>  
 <span data-ttu-id="c9db0-204">Il comando che segue visualizza un archivio di sistema predefinito denominato `my` con output dettagliato.</span><span class="sxs-lookup"><span data-stu-id="c9db0-204">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="c9db0-205">Il comando che segue aggiunge tutti i certificati contenuti in un file denominato `myFile.ext` in un nuovo file denominato `newFile.ext`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-205">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="c9db0-206">Il comando che segue aggiunge il certificato contenuto in un file denominato `testcert.cer` all'archivio di sistema `my`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-206">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="c9db0-207">Il comando che segue aggiunge il certificato contenuto in un file denominato `TrustedCert.cer` all'archivio certificati radice.</span><span class="sxs-lookup"><span data-stu-id="c9db0-207">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="c9db0-208">Il comando che segue salva un certificato con il nome comune `myCert` contenuto nell'archivio di sistema `my` in un file denominato `newCert.cer`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-208">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="c9db0-209">Il comando che segue elimina tutti gli elenchi di scopi consentiti contenuti nell'archivio di sistema `my` e salva l'archivio ottenuto in un file denominato `newStore.str`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-209">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="c9db0-210">Il comando che segue salva nel file `my` un certificato contenuto nell'archivio di sistema `newFile`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-210">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="c9db0-211">Verrà chiesto di inserire il numero del certificato presente in `my` per inserirlo in `newFile`.</span><span class="sxs-lookup"><span data-stu-id="c9db0-211">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9db0-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9db0-212">See Also</span></span>  
 <span data-ttu-id="c9db0-213">[Strumenti](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="c9db0-213">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="c9db0-214">[Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)  (Makecert.exe, strumento di creazione certificati)</span><span class="sxs-lookup"><span data-stu-id="c9db0-214">[Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span></span>  
 [<span data-ttu-id="c9db0-215">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="c9db0-215">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

