---
title: Cert2spc.exe (strumento di test dei certificati del distributore di software)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b0ef0072e6e9a1e9f4a28d6e19894f301fe3fc0
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864800"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="d959f-102">Cert2spc.exe (strumento di test dei certificati del distributore di software)</span><span class="sxs-lookup"><span data-stu-id="d959f-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="d959f-103">Lo strumento di verifica dei certificati dell'editore del software (Cert2spc.exe) crea un certificato SPC (Software Publisher's Certificate) da uno o più certificati X.509</span><span class="sxs-lookup"><span data-stu-id="d959f-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="d959f-104">ed è finalizzato unicamente ai test.</span><span class="sxs-lookup"><span data-stu-id="d959f-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="d959f-105">È possibile ottenere un certificato SPC valido da un'autorità di certificazione quale VeriSign o Thawte.</span><span class="sxs-lookup"><span data-stu-id="d959f-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="d959f-106">Per ulteriori informazioni sulla creazione di certificati X.509, vedere [Makecert.exe (Certificate Creation Tool)](https://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) (Makecert.exe, strumento di creazione dei comandi).</span><span class="sxs-lookup"><span data-stu-id="d959f-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](https://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).</span></span>  
  
 <span data-ttu-id="d959f-107">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d959f-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="d959f-108">Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d959f-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="d959f-109">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d959f-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="d959f-110">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d959f-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d959f-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d959f-111">Syntax</span></span>  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d959f-112">Parametri</span><span class="sxs-lookup"><span data-stu-id="d959f-112">Parameters</span></span>  
  
|<span data-ttu-id="d959f-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="d959f-113">Argument</span></span>|<span data-ttu-id="d959f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d959f-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="d959f-115">Il nome di un certificato X.509 da includere nel file SPC.</span><span class="sxs-lookup"><span data-stu-id="d959f-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="d959f-116">È possibile specificare più nomi separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="d959f-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="d959f-117">Il nome di un elenco di revoche di certificati da includere nel file SPC.</span><span class="sxs-lookup"><span data-stu-id="d959f-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="d959f-118">È possibile specificare più nomi separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="d959f-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="d959f-119">Il nome dell'oggetto PKCS #7 che conterrà i certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="d959f-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="d959f-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="d959f-120">Option</span></span>|<span data-ttu-id="d959f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d959f-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d959f-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="d959f-122">**/?**</span></span>|<span data-ttu-id="d959f-123">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="d959f-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="d959f-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="d959f-124">Examples</span></span>  
 <span data-ttu-id="d959f-125">Il comando che segue crea un certificato SPC da `myCertificate.cer` e lo inserisce in `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="d959f-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="d959f-126">Il comando che segue crea un certificato SPC da `oneCertificate.cer` e `twoCertificate.cer` e lo inserisce in `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="d959f-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="d959f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d959f-127">See Also</span></span>  
 [<span data-ttu-id="d959f-128">Strumenti</span><span class="sxs-lookup"><span data-stu-id="d959f-128">Tools</span></span>](../../../docs/framework/tools/index.md)  
 <span data-ttu-id="d959f-129">[Makecert.exe (Certificate Creation Tool)](https://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) (Makecert.exe, strumento di creazione certificati)</span><span class="sxs-lookup"><span data-stu-id="d959f-129">[Makecert.exe (Certificate Creation Tool)](https://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)</span></span>  
 [<span data-ttu-id="d959f-130">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="d959f-130">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
