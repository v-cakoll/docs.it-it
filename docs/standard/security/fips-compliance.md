---
title: Conformità FIPS-.NET Core
description: Viene illustrata la conformità a .NET Core Federal Information Processing Standard (FIPS).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: 84d6edc6975af0484bb67999ad5891eaf4db057d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626958"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="f8981-103">Conformità a .NET Core Federal Information Processing Standard (FIPS)</span><span class="sxs-lookup"><span data-stu-id="f8981-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="f8981-104">La pubblicazione di Federal Information Processing Standard (FIPS) 140-2 è uno standard governativo degli Stati Uniti che definisce i requisiti di sicurezza minimi per i moduli di crittografia nei prodotti Information Technology, come definito nella sezione 5131 delle informazioni Act of 1996, Technology Management Reform.</span><span class="sxs-lookup"><span data-stu-id="f8981-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="f8981-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="f8981-105">.NET Core:</span></span>

* <span data-ttu-id="f8981-106">Passa le chiamate delle primitive crittografiche ai moduli standard forniti dal sistema operativo sottostante.</span><span class="sxs-lookup"><span data-stu-id="f8981-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="f8981-107">Non **impone l'** uso di algoritmi o dimensioni delle chiavi approvate da FIPS nelle app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f8981-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="f8981-108">L'amministratore di sistema è responsabile della configurazione della conformità FIPS per un sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f8981-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="f8981-109">Se il codice viene scritto per un ambiente conforme a FIPS, lo sviluppatore è responsabile di garantire che non vengano usati algoritmi FIPS non conformi.</span><span class="sxs-lookup"><span data-stu-id="f8981-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="f8981-110">Per ulteriori informazioni sulla conformità FIPS, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8981-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="f8981-111">Conformità FIPS di Windows</span><span class="sxs-lookup"><span data-stu-id="f8981-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="f8981-112">Configurazione di Windows per la conformità FIPS</span><span class="sxs-lookup"><span data-stu-id="f8981-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="f8981-113">Capitolo 8. Standard e normative federali Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="f8981-113">Chapter 8. Federal Standards and Regulations Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
