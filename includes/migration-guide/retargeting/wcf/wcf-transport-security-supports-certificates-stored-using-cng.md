---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614497"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a><span data-ttu-id="d61aa-101">La sicurezza del trasporto WCF supporta i certificati archiviati usando CNG</span><span class="sxs-lookup"><span data-stu-id="d61aa-101">WCF transport security supports certificates stored using CNG</span></span>

#### <a name="details"></a><span data-ttu-id="d61aa-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d61aa-102">Details</span></span>

<span data-ttu-id="d61aa-103">A partire dalle applicazioni che hanno come destinazione .NET Framework 4.6.2, la sicurezza del trasporto WCF supporta i certificati archiviati usando la libreria di crittografia di Windows (CNG).</span><span class="sxs-lookup"><span data-stu-id="d61aa-103">Starting with apps that target the .NET Framework 4.6.2, WCF transport security supports certificates stored using the Windows Cryptography Library (CNG).</span></span> <span data-ttu-id="d61aa-104">Questo supporto è limitato ai certificati con una chiave pubblica che ha un esponente di lunghezza non superiore a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="d61aa-104">This support is limited to certificates with a public key that has an exponent no more than 32 bits in length.</span></span> <span data-ttu-id="d61aa-105">Quando un'applicazione è destinata a .NET Framework 4.6.2, questa funzionalità è attivata per impostazione predefinita. Nelle versioni precedenti di .NET Framework il tentativo di usare i certificati X509 con un provider di archiviazione chiavi CSG genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d61aa-105">When an application targets the .NET Framework 4.6.2, this feature is on by default.In earlier versions of the .NET Framework, the attempt to use X509 certificates with a CSG key storage provider throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d61aa-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d61aa-106">Suggestion</span></span>

<span data-ttu-id="d61aa-107">Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma eseguite in .NET Framework 4.6.2 abilitano il supporto per i certificati CNG aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="d61aa-107">Apps that target the .NET Framework 4.6.1 and earlier but are running on the .NET Framework 4.6.2 can enable support for CNG certificates by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

<span data-ttu-id="d61aa-108">L'operazione può essere eseguita anche con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d61aa-108">This can also be done programmatically with the following code:</span></span>

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

<span data-ttu-id="d61aa-109">Si noti che, grazie a questa modifica, i codici di gestione delle eccezioni che dipendono dal tentativo di avviare una comunicazione protetta con un certificato CNG di esito negativo non verranno più eseguiti.</span><span class="sxs-lookup"><span data-stu-id="d61aa-109">Note that, because of this change, any exception handling code that depends on the attempt to initiate secure communication with a CNG certificate to fail will no longer execute.</span></span>

| <span data-ttu-id="d61aa-110">Nome</span><span class="sxs-lookup"><span data-stu-id="d61aa-110">Name</span></span>    | <span data-ttu-id="d61aa-111">Valore</span><span class="sxs-lookup"><span data-stu-id="d61aa-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d61aa-112">Scope</span><span class="sxs-lookup"><span data-stu-id="d61aa-112">Scope</span></span>   | <span data-ttu-id="d61aa-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="d61aa-113">Minor</span></span>       |
| <span data-ttu-id="d61aa-114">Version</span><span class="sxs-lookup"><span data-stu-id="d61aa-114">Version</span></span> | <span data-ttu-id="d61aa-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d61aa-115">4.6.2</span></span>       |
| <span data-ttu-id="d61aa-116">Type</span><span class="sxs-lookup"><span data-stu-id="d61aa-116">Type</span></span>    | <span data-ttu-id="d61aa-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d61aa-117">Retargeting</span></span> |
