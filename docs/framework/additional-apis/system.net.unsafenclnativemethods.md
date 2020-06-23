---
title: Classe UnsafeNclNativeMethods (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990359"
---
# <a name="unsafenclnativemethods-class"></a><span data-ttu-id="83123-102">Classe UnsafeNclNativeMethods</span><span class="sxs-lookup"><span data-stu-id="83123-102">UnsafeNclNativeMethods class</span></span>

<span data-ttu-id="83123-103">Contiene classi che importano metodi di rete nativi non sicuri.</span><span class="sxs-lookup"><span data-stu-id="83123-103">Contains classes that import unsafe native networking methods.</span></span> <span data-ttu-id="83123-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="83123-104">This class cannot be inherited.</span></span>

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> <span data-ttu-id="83123-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="83123-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="83123-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="83123-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="nativepki-class"></a><span data-ttu-id="83123-107">Classe NativePKI</span><span class="sxs-lookup"><span data-stu-id="83123-107">NativePKI class</span></span>

<span data-ttu-id="83123-108">Contiene i metodi importati da crypt32.dll.</span><span class="sxs-lookup"><span data-stu-id="83123-108">Contains methods imported from crypt32.dll.</span></span> <span data-ttu-id="83123-109">Questi metodi gestiscono i certificati quando si usa Hypertext Transfer Protocol Secure (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="83123-109">These methods handle certificates when using Hypertext Transfer Protocol Secure (HTTPS).</span></span> <span data-ttu-id="83123-110">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="83123-110">This class cannot be inherited.</span></span>

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a><span data-ttu-id="83123-111">NativePKI. FindClientCertificates, metodo</span><span class="sxs-lookup"><span data-stu-id="83123-111">NativePKI.FindClientCertificates method</span></span>

<span data-ttu-id="83123-112">Individua i certificati client disponibili da inviare al server.</span><span class="sxs-lookup"><span data-stu-id="83123-112">Discovers available client certificates to send to the server.</span></span>

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a><span data-ttu-id="83123-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83123-113">Return value</span></span>

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

<span data-ttu-id="83123-114">Raccolta di certificati client disponibili.</span><span class="sxs-lookup"><span data-stu-id="83123-114">A collection of available client certificates.</span></span>

## <a name="requirements"></a><span data-ttu-id="83123-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83123-115">Requirements</span></span>

<span data-ttu-id="83123-116">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="83123-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="83123-117">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="83123-117">**Assembly:** System (in System.dll)</span></span>
