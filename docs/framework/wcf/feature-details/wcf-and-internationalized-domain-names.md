---
title: WCF e nomi IDN (Internationalized Domain Name)
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 1db62f3e7d073fd1bf9bf9d4d0e17703310f2e69
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988584"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="d2368-102">WCF e nomi IDN (Internationalized Domain Name)</span><span class="sxs-lookup"><span data-stu-id="d2368-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="d2368-103">È stato aggiunto il supporto per i servizi WCF con gli IDN (Internationalized Domain Name).</span><span class="sxs-lookup"><span data-stu-id="d2368-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="d2368-104">Un IDN è un nome di dominio che contiene caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="d2368-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="d2368-105">Questo supporto include sia la possibilità di ospitare un servizio WCF con un nome IDN sia un client WCF per comunicare con un servizio Web con un nome IDN.</span><span class="sxs-lookup"><span data-stu-id="d2368-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="d2368-106">System.Uri e IDN</span><span class="sxs-lookup"><span data-stu-id="d2368-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="d2368-107">All'oggetto <xref:System.Uri> sono associate due proprietà: <xref:System.Uri.Host%2A> e <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2368-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="d2368-108">Queste proprietà contengono valori Unicode o Punycode in base alle impostazioni di configurazione IDN.</span><span class="sxs-lookup"><span data-stu-id="d2368-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="d2368-109">IDN viene abilitato nel file di configurazione di un'applicazione usando il seguente codice XML</span><span class="sxs-lookup"><span data-stu-id="d2368-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="d2368-110">L' \<elemento > IDN contiene l'attributo enabled che può essere impostato su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2368-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1. <span data-ttu-id="d2368-111">"None"</span><span class="sxs-lookup"><span data-stu-id="d2368-111">"None"</span></span>  
  
2. <span data-ttu-id="d2368-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="d2368-112">"AllExceptIntranet"</span></span>  
  
3. <span data-ttu-id="d2368-113">Tutti</span><span class="sxs-lookup"><span data-stu-id="d2368-113">"All"</span></span>  
  
 <span data-ttu-id="d2368-114">Quando l'impostazione IDN è impostata su "None", nessuna conversione viene eseguita da URI. host o URI. DnsSafeHost.</span><span class="sxs-lookup"><span data-stu-id="d2368-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="d2368-115">Quando l'impostazione IDN è impostata su "All", Uri. L'host rimane Unicode e l'URI. DnsSafeHost viene convertito in Punycode.</span><span class="sxs-lookup"><span data-stu-id="d2368-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="d2368-116">Quando l'impostazione IDN è impostata su "AllExceptIntranet", Uri. DnsSafeHost viene convertito in Punycode per gli indirizzi Internet e rimane Unicode per gli indirizzi Intranet.</span><span class="sxs-lookup"><span data-stu-id="d2368-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="d2368-117">Questa impostazione è importante per una corretta risoluzione dei nomi DNS.</span><span class="sxs-lookup"><span data-stu-id="d2368-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="d2368-118">Si noti che questa impostazione non deve essere configurata per Windows 8 e versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="d2368-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="d2368-119">È consigliabile non impostare mai come hardcoded un indirizzo in cui viene usato Punycode.</span><span class="sxs-lookup"><span data-stu-id="d2368-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="d2368-120">WCF lo convertirà in base alle impostazioni di configurazione che vengano applicate.</span><span class="sxs-lookup"><span data-stu-id="d2368-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="d2368-121">Quando si aggiungono caratteri Unicode ad applicationHost.exe.config, salvare il file usando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d2368-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2368-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2368-122">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
