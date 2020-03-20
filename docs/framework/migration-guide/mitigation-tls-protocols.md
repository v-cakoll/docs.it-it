---
title: 'Mitigazione: Protocolli TLS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457832"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="a934a-102">Mitigazione: Protocolli TLS</span><span class="sxs-lookup"><span data-stu-id="a934a-102">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="a934a-103">A partire da .NET Framework 4.6, le classi <xref:System.Net.ServicePointManager?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType> possono usare uno dei tre protocolli seguenti: Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="a934a-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="a934a-104">Il protocollo SSL 3.0 e la crittografia RC4 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="a934a-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a934a-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="a934a-105">Impact</span></span>  
 <span data-ttu-id="a934a-106">Questa modifica interessa:</span><span class="sxs-lookup"><span data-stu-id="a934a-106">This change affects:</span></span>  
  
- <span data-ttu-id="a934a-107">Qualsiasi app che usa SSL per comunicare con un server HTTPS o un server socket tramite uno qualsiasi dei tipi seguenti: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> e <xref:System.Net.Security.SslStream>.</span><span class="sxs-lookup"><span data-stu-id="a934a-107">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
- <span data-ttu-id="a934a-108">Qualsiasi app sul lato server che non può essere aggiornata per supportare Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="a934a-108">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a934a-109">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="a934a-109">Mitigation</span></span>  
 <span data-ttu-id="a934a-110">L'attenuazione consigliata consiste nell'aggiornare l'app sul lato server a Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="a934a-110">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="a934a-111">Se ciò non è fattibile o se le app client non funzionano, è possibile usare la classe <xref:System.AppContext> per rifiutare esplicitamente questa funzionalità in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a934a-111">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
- <span data-ttu-id="a934a-112">A livello di codice, usando un frammento di codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a934a-112">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="a934a-113">Poiché l'oggetto <xref:System.Net.ServicePointManager> viene inizializzato una sola volta, la definizione di queste impostazioni di compatibilità deve essere la prima attività eseguita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a934a-113">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
- <span data-ttu-id="a934a-114">Aggiungendo la riga seguente [ \<](../configure-apps/file-schema/runtime/runtime-element.md) alla sezione runtime>del file app.config:</span><span class="sxs-lookup"><span data-stu-id="a934a-114">By adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="a934a-115">Si noti, tuttavia, che il rifiuto esplicito del comportamento non è consigliabile, in quanto rende meno sicura l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a934a-115">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a934a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a934a-116">See also</span></span>

- [<span data-ttu-id="a934a-117">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="a934a-117">Application compatibility</span></span>](application-compatibility.md)
