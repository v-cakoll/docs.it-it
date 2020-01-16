---
title: 'Procedura: ottenere un certificato (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: bfe6dcfe6850ee17a7bbb59f3a6ccad6c3c3e7d7
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964236"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="a93b1-102">Procedura: ottenere un certificato (WCF)</span><span class="sxs-lookup"><span data-stu-id="a93b1-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="a93b1-103">Per usare una delle funzionalità di Windows Communication Foundation (WCF) di che usano certificati X. 509, è sufficiente ottenere prima i certificati.</span><span class="sxs-lookup"><span data-stu-id="a93b1-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="a93b1-104">Per ottenere un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="a93b1-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="a93b1-105">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="a93b1-105">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="a93b1-106">Acquistare un certificato da un'autorità di certificazione, ad esempio VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="a93b1-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="a93b1-107">Configurare il proprio servizio certificati e fare in modo che un'autorità di certificazione firmi i certificati.</span><span class="sxs-lookup"><span data-stu-id="a93b1-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> <span data-ttu-id="a93b1-108">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter e Windows 2000 Datacenter Server includono tutti servizi certificati che supportano l'infrastruttura a chiave pubblica (PKI).</span><span class="sxs-lookup"><span data-stu-id="a93b1-108">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="a93b1-109">In Windows Server 2008 usare il ruolo [Servizi certificati Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) per gestire un'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="a93b1-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="a93b1-110">Configurare un proprio servizio certificati e non far firmare i certificati.</span><span class="sxs-lookup"><span data-stu-id="a93b1-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a93b1-111">Indipendentemente dall'approccio adottato, il destinatario della richiesta SOAP che contiene il certificato X.509 deve considerare attendibile il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="a93b1-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="a93b1-112">Questo significa che il certificato X.509 o un'autorità emittente nella catena di certificati si trova nell'archivio certificati Persone attendibili e che il certificato X.509 non si trova nell'archivio Certificati non disponibili nell'elenco locale.</span><span class="sxs-lookup"><span data-stu-id="a93b1-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93b1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a93b1-113">See also</span></span>

- [<span data-ttu-id="a93b1-114">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="a93b1-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a93b1-115">Procedura: Creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="a93b1-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
