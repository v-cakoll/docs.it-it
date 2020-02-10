---
title: Modifiche di rilievo della crittografia
description: Elenca le modifiche di rilievo correlate alla crittografia in .NET Core.
ms.date: 09/20/2019
ms.openlocfilehash: fcef4b65245a5dd9219cbdbb548ca575a823a949
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093032"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="a68f6-103">Modifiche di rilievo della crittografia</span><span class="sxs-lookup"><span data-stu-id="a68f6-103">Cryptography breaking changes</span></span>

<span data-ttu-id="a68f6-104">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="a68f6-104">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="a68f6-105">Il valore predefinito di EnvelopedCms è AES-256 Encryption</span><span class="sxs-lookup"><span data-stu-id="a68f6-105">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption)
- [<span data-ttu-id="a68f6-106">Dimensioni minime per la generazione della chiave RSAOpenSsl aumentata</span><span class="sxs-lookup"><span data-stu-id="a68f6-106">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased)
- [<span data-ttu-id="a68f6-107">.NET Core 3,0 preferisce OpenSSL 1.1. x a OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="a68f6-107">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x)
- [<span data-ttu-id="a68f6-108">Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="a68f6-108">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor)

## <a name="net-core-30"></a><span data-ttu-id="a68f6-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a68f6-109">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

## <a name="net-core-30-preview-9"></a><span data-ttu-id="a68f6-110">.NET Core 3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="a68f6-110">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***
