---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616261"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a><span data-ttu-id="224ce-101">Le classi di crittografia gestite non generano un'eccezione CryptographyException in modalità FIPS</span><span class="sxs-lookup"><span data-stu-id="224ce-101">Managed cryptography classes do not throw a CryptographyException in FIPS mode</span></span>

#### <a name="details"></a><span data-ttu-id="224ce-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="224ce-102">Details</span></span>

<span data-ttu-id="224ce-103">In .NET Framework 4.7.2 e versioni precedenti le classi del provider del servizio di crittografia gestite, ad esempio <xref:System.Security.Cryptography.SHA256Managed>, generano un'eccezione <xref:System.Security.Cryptography.CryptographicException> quando le librerie di crittografia del sistema sono configurate in modalità FIPS.</span><span class="sxs-lookup"><span data-stu-id="224ce-103">In .NET Framework 4.7.2 and earlier versions, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in FIPS mode.</span></span> <span data-ttu-id="224ce-104">Queste eccezioni vengono generate perché le versioni gestite non sono state sottoposte alla certificazione FIPS (Federal Information Processing Standards) 140-2, nonché per bloccare gli algoritmi di crittografia che non sono stati approvati in base alle regole FIPS.</span><span class="sxs-lookup"><span data-stu-id="224ce-104">These exceptions are thrown because the managed versions have not undergone FIPS (Federal Information Processing Standards) 140-2 certification, as well as to block cryptographic algorithms that were not considered to be approved based on the FIPS rules.</span></span>  <span data-ttu-id="224ce-105">Poiché sono pochi gli sviluppatori che hanno i computer di sviluppo in modalità FIPS, queste eccezioni vengono spesso generate solo nei sistemi di produzione.Le applicazioni destinate a .NET Framework 4.8 e versioni successive passano automaticamente ai nuovi criteri, meno stretti, quindi in questi casi non viene più generata un'eccezione <xref:System.Security.Cryptography.CryptographicException> per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="224ce-105">Because few developers have their development machines in FIPS mode, these exceptions are frequently thrown only on production systems.Applications that target .NET Framework 4.8 and later versions automatically switch to the newer, relaxed policy, so that a <xref:System.Security.Cryptography.CryptographicException> is no longer thrown by default in such cases.</span></span> <span data-ttu-id="224ce-106">Al contrario, le classi di crittografia gestite reindirizzano le operazioni di crittografia a una libreria di crittografia del sistema.</span><span class="sxs-lookup"><span data-stu-id="224ce-106">Instead, the managed cryptography classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="224ce-107">Questa modifica dei criteri rimuove in modo efficiente una differenza potenzialmente fuorviante tra ambienti di sviluppo e ambienti di produzione e rende possibile eseguire i componenti nativi e i componenti gestiti in base agli stessi criteri di crittografia.</span><span class="sxs-lookup"><span data-stu-id="224ce-107">This policy change effectively removes a potentially confusing difference between developer environments and the production environments and makes native components and managed components operate under the same cryptographic policy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="224ce-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="224ce-108">Suggestion</span></span>

<span data-ttu-id="224ce-109">Se questo comportamento è indesiderato, è possibile rifiutarlo esplicitamente e ripristinare il comportamento precedente in modo che venga generata un'eccezione <xref:System.Security.Cryptography.CryptographicException> in modalità FIPS aggiungendo l'impostazione di configurazione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="224ce-109">If this behavior is undesirable, you can opt out of it and restore the previous behavior so that a <xref:System.Security.Cryptography.CryptographicException> is thrown in FIPS mode by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

<span data-ttu-id="224ce-110">Se l'applicazione è destinata a .NET Framework 4.7.2 o versioni precedenti, è possibile acconsentire esplicitamente a questa modifica aggiungendo l'impostazione di configurazione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="224ce-110">If your application targets .NET Framework 4.7.2 or earlier, you can also opt in to this change by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| <span data-ttu-id="224ce-111">Nome</span><span class="sxs-lookup"><span data-stu-id="224ce-111">Name</span></span>    | <span data-ttu-id="224ce-112">Valore</span><span class="sxs-lookup"><span data-stu-id="224ce-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="224ce-113">Scope</span><span class="sxs-lookup"><span data-stu-id="224ce-113">Scope</span></span>   | <span data-ttu-id="224ce-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="224ce-114">Edge</span></span>        |
| <span data-ttu-id="224ce-115">Version</span><span class="sxs-lookup"><span data-stu-id="224ce-115">Version</span></span> | <span data-ttu-id="224ce-116">4.8</span><span class="sxs-lookup"><span data-stu-id="224ce-116">4.8</span></span>         |
| <span data-ttu-id="224ce-117">Type</span><span class="sxs-lookup"><span data-stu-id="224ce-117">Type</span></span>    | <span data-ttu-id="224ce-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="224ce-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="224ce-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="224ce-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
