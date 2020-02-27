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
* [Capitolo 8. Standard e normative federali Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
