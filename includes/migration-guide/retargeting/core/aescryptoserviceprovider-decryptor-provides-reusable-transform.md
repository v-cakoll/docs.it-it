---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614441"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a><span data-ttu-id="bc8d2-101">Il componente di decrittografia AesCryptoServiceProvider fornisce una trasformazione riutilizzabile</span><span class="sxs-lookup"><span data-stu-id="bc8d2-101">AesCryptoServiceProvider decryptor provides a reusable transform</span></span>

#### <a name="details"></a><span data-ttu-id="bc8d2-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bc8d2-102">Details</span></span>

<span data-ttu-id="bc8d2-103">A partire dalle app destinate a .NET Framework 4.6.2, il componente di decrittografia <xref:System.Security.Cryptography.AesCryptoServiceProvider> fornisce una trasformazione riutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="bc8d2-103">Starting with apps that target the .NET Framework 4.6.2, the <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor provides a reusable transform.</span></span> <span data-ttu-id="bc8d2-104">Dopo una chiamata a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, la trasformazione viene reinizializzata e può essere riutilizzata.</span><span class="sxs-lookup"><span data-stu-id="bc8d2-104">After a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, the transform is reinitialized and can be reused.</span></span> <span data-ttu-id="bc8d2-105">Per le app destinate a versioni precedenti di .NET Framework, il tentativo di riusare il componente di decrittografia chiamando <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> dopo una chiamata a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> genera un'eccezione <xref:System.Security.Cryptography.CryptographicException> o produce dati danneggiati.</span><span class="sxs-lookup"><span data-stu-id="bc8d2-105">For apps that target earlier versions of the .NET Framework, attempting to reuse the decryptor by calling <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> after a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> throws a <xref:System.Security.Cryptography.CryptographicException> or produces corrupted data.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bc8d2-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="bc8d2-106">Suggestion</span></span>

<span data-ttu-id="bc8d2-107">L'impatto di questa modifica dovrebbe essere minimo, dato che questo è il comportamento previsto. Le applicazioni che dipendono dal comportamento precedente lo possono rifiutare esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bc8d2-107">The impact of this change should be minimal, since this is the expected behavior.Applications that depend on the previous behavior can opt out of it using it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

<span data-ttu-id="bc8d2-108">Le applicazioni destinate a versioni precedenti di .NET Framework ma in esecuzione su una versione uguale o successiva a .NET Framework .NET Framework 4.6.2 possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bc8d2-108">In addition, applications that target a previous version of the .NET Framework but are running under a version of the .NET Framework starting with .NET Framework 4.6.2 can opt in to it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| <span data-ttu-id="bc8d2-109">Nome</span><span class="sxs-lookup"><span data-stu-id="bc8d2-109">Name</span></span>    | <span data-ttu-id="bc8d2-110">Valore</span><span class="sxs-lookup"><span data-stu-id="bc8d2-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bc8d2-111">Scope</span><span class="sxs-lookup"><span data-stu-id="bc8d2-111">Scope</span></span>   | <span data-ttu-id="bc8d2-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="bc8d2-112">Minor</span></span>       |
| <span data-ttu-id="bc8d2-113">Version</span><span class="sxs-lookup"><span data-stu-id="bc8d2-113">Version</span></span> | <span data-ttu-id="bc8d2-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="bc8d2-114">4.6.2</span></span>       |
| <span data-ttu-id="bc8d2-115">Type</span><span class="sxs-lookup"><span data-stu-id="bc8d2-115">Type</span></span>    | <span data-ttu-id="bc8d2-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="bc8d2-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bc8d2-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="bc8d2-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
