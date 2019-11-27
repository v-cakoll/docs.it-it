---
title: Conformità FIPS-.NET Core
description: Viene illustrata la conformità a .NET Core Federal Information Processing Standard (FIPS).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205066"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>Conformità a .NET Core Federal Information Processing Standard (FIPS)

La pubblicazione di Federal Information Processing Standard (FIPS) 140-2 è uno standard governativo degli Stati Uniti che definisce i requisiti di sicurezza minimi per i moduli di crittografia nei prodotti Information Technology, come definito nella sezione 5131 delle informazioni Act of 1996, Technology Management Reform.

.NET Core:

* Passa le chiamate delle primitive crittografiche ai moduli standard forniti dal sistema operativo sottostante.
* Non **impone l'** uso di algoritmi o dimensioni delle chiavi approvate da FIPS nelle app .NET Core.

L'amministratore di sistema è responsabile della configurazione della conformità FIPS per un sistema operativo.

Se il codice viene scritto per un ambiente conforme a FIPS, lo sviluppatore è responsabile di garantire che non vengano usati algoritmi FIPS non conformi.

Per ulteriori informazioni sulla conformità FIPS, vedere gli articoli seguenti:

* [Conformità FIPS di Windows](/windows/security/threat-protection/fips-140-validation)
* [Configurazione di Windows per la conformità FIPS](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [10,2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
