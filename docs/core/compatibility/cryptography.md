---
title: Modifiche di rilievo della crittografia
description: Elenca le modifiche di rilievo correlate alla crittografia in .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: 66049473083d87b4c84408f35a04193a4563c2b3
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135601"
---
# <a name="cryptography-breaking-changes"></a>Modifiche di rilievo della crittografia

In questa pagina sono documentate le modifiche di rilievo seguenti:

| Modifica | Versione introdotta |
| - | :-: |
| [La sintassi di avvio del certificato ATTENDIBILe non è più supportata in Linux](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | 3.0 |
| [Il valore predefinito di EnvelopedCms è AES-256 Encryption](#envelopedcms-defaults-to-aes-256-encryption) | 3.0 |
| [Dimensioni minime per la generazione della chiave RSAOpenSsl aumentata](#minimum-size-for-rsaopenssl-key-generation-has-increased) | 3.0 |
| [.NET Core 3,0 preferisce OpenSSL 1.1. x a OpenSSL 1.0. x](#net-core-30-prefers-openssl-11x-to-openssl-10x) | 3.0 |
| [Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | 3.0 |
| [Il parametro booleano di SignedCms. ComputeSignature è rispettato](#boolean-parameter-of-signedcmscomputesignature-is-respected) | 2.1 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
