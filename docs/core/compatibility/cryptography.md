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
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="d9c95-103">Modifiche di rilievo della crittografia</span><span class="sxs-lookup"><span data-stu-id="d9c95-103">Cryptography breaking changes</span></span>

<span data-ttu-id="d9c95-104">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9c95-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="d9c95-105">Modifica</span><span class="sxs-lookup"><span data-stu-id="d9c95-105">Breaking change</span></span> | <span data-ttu-id="d9c95-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d9c95-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="d9c95-107">La sintassi di avvio del certificato ATTENDIBILe non è più supportata in Linux</span><span class="sxs-lookup"><span data-stu-id="d9c95-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="d9c95-108">3.0</span><span class="sxs-lookup"><span data-stu-id="d9c95-108">3.0</span></span> |
| [<span data-ttu-id="d9c95-109">Il valore predefinito di EnvelopedCms è AES-256 Encryption</span><span class="sxs-lookup"><span data-stu-id="d9c95-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="d9c95-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d9c95-110">3.0</span></span> |
| [<span data-ttu-id="d9c95-111">Dimensioni minime per la generazione della chiave RSAOpenSsl aumentata</span><span class="sxs-lookup"><span data-stu-id="d9c95-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="d9c95-112">3.0</span><span class="sxs-lookup"><span data-stu-id="d9c95-112">3.0</span></span> |
| [<span data-ttu-id="d9c95-113">.NET Core 3,0 preferisce OpenSSL 1.1. x a OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="d9c95-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="d9c95-114">3.0</span><span class="sxs-lookup"><span data-stu-id="d9c95-114">3.0</span></span> |
| [<span data-ttu-id="d9c95-115">Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d9c95-115">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | <span data-ttu-id="d9c95-116">3.0</span><span class="sxs-lookup"><span data-stu-id="d9c95-116">3.0</span></span> |
| [<span data-ttu-id="d9c95-117">Il parametro booleano di SignedCms. ComputeSignature è rispettato</span><span class="sxs-lookup"><span data-stu-id="d9c95-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="d9c95-118">2.1</span><span class="sxs-lookup"><span data-stu-id="d9c95-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="d9c95-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d9c95-119">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="d9c95-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d9c95-120">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
