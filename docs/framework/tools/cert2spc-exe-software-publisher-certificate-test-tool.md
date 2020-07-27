---
title: Cert2spc.exe (strumento di test dei certificati del distributore di software)
description: Utilizzare Cert2spc.exe, lo strumento di test dei certificati dell'editore di software. Questo strumento crea un certificato dell'editore del software (SPC) da uno o più certificati X. 509.
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
ms.openlocfilehash: 2eb6339aa6f5d23a5b87986410cbeaac2dac2bec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167320"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="2e691-104">Cert2spc.exe (strumento di test dei certificati del distributore di software)</span><span class="sxs-lookup"><span data-stu-id="2e691-104">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="2e691-105">Lo strumento di verifica dei certificati dell'editore del software (Cert2spc.exe) crea un certificato SPC (Software Publisher's Certificate) da uno o più certificati X.509</span><span class="sxs-lookup"><span data-stu-id="2e691-105">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="2e691-106">ed è finalizzato unicamente ai test.</span><span class="sxs-lookup"><span data-stu-id="2e691-106">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="2e691-107">È possibile ottenere un certificato SPC valido da un'autorità di certificazione quale VeriSign o Thawte.</span><span class="sxs-lookup"><span data-stu-id="2e691-107">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="2e691-108">Per ulteriori informazioni sulla creazione di certificati X.509, vedere [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione dei comandi).</span><span class="sxs-lookup"><span data-stu-id="2e691-108">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="2e691-109">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e691-109">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="2e691-110">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="2e691-110">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="2e691-111">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2e691-111">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="2e691-112">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2e691-112">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e691-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e691-113">Syntax</span></span>  
  
```console  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e691-114">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e691-114">Parameters</span></span>  
  
|<span data-ttu-id="2e691-115">Argomento</span><span class="sxs-lookup"><span data-stu-id="2e691-115">Argument</span></span>|<span data-ttu-id="2e691-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e691-116">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="2e691-117">Il nome di un certificato X.509 da includere nel file SPC.</span><span class="sxs-lookup"><span data-stu-id="2e691-117">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="2e691-118">È possibile specificare più nomi separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="2e691-118">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="2e691-119">Il nome di un elenco di revoche di certificati da includere nel file SPC.</span><span class="sxs-lookup"><span data-stu-id="2e691-119">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="2e691-120">È possibile specificare più nomi separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="2e691-120">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="2e691-121">Il nome dell'oggetto PKCS #7 che conterrà i certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="2e691-121">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="2e691-122">Opzione</span><span class="sxs-lookup"><span data-stu-id="2e691-122">Option</span></span>|<span data-ttu-id="2e691-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e691-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2e691-124">**/?**</span><span class="sxs-lookup"><span data-stu-id="2e691-124">**/?**</span></span>|<span data-ttu-id="2e691-125">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="2e691-125">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="2e691-126">Esempi</span><span class="sxs-lookup"><span data-stu-id="2e691-126">Examples</span></span>  
 <span data-ttu-id="2e691-127">Il comando che segue crea un certificato SPC da `myCertificate.cer` e lo inserisce in `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="2e691-127">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="2e691-128">Il comando che segue crea un certificato SPC da `oneCertificate.cer` e `twoCertificate.cer` e lo inserisce in `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="2e691-128">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e691-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e691-129">See also</span></span>

- [<span data-ttu-id="2e691-130">Strumenti</span><span class="sxs-lookup"><span data-stu-id="2e691-130">Tools</span></span>](index.md)
- <span data-ttu-id="2e691-131">[Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione certificati)</span><span class="sxs-lookup"><span data-stu-id="2e691-131">[Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert)</span></span>
- [<span data-ttu-id="2e691-132">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="2e691-132">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
