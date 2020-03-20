---
title: "Procedura: Impostare criteri di cache predefiniti basati sull'ora per un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
ms.openlocfilehash: 0aaa26f67ef1ef191060e682690fa14de328b812
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048097"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="9fb1b-102">Procedura: Impostare criteri di cache predefiniti basati sull'ora per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="9fb1b-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="9fb1b-103">I criteri di cache predefiniti basati sul tempo consentono di definire il comportamento della cache per un'applicazione in base alle intestazioni inviate con la risorsa memorizzata nella cache e al comportamento della cache definito nelle sezioni 13 e 14 del documento RFC 2616, disponibile nel sito Web [Internet Engineering Task Force (IETF)](https://www.ietf.org/).</span><span class="sxs-lookup"><span data-stu-id="9fb1b-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="9fb1b-104">Questo è il comportamento della cache appropriato per la maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9fb1b-104">This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="9fb1b-105">Per impostare i criteri automatici predefiniti per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="9fb1b-105">To set the default automatic policy for an application</span></span>  
  
1. <span data-ttu-id="9fb1b-106">Creare un oggetto criteri basati sul tempo predefinito.</span><span class="sxs-lookup"><span data-stu-id="9fb1b-106">Create a default time-based policy object.</span></span>  
  
2. <span data-ttu-id="9fb1b-107">Impostare l'oggetto criteri come predefinito per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9fb1b-107">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fb1b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9fb1b-108">Example</span></span>  
 <span data-ttu-id="9fb1b-109">I due esempi in questa sezione producono criteri identici.</span><span class="sxs-lookup"><span data-stu-id="9fb1b-109">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="9fb1b-110">L'esempio seguente crea un criterio basato sul tempo predefinito e lo imposta come predefinito per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9fb1b-110">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 <span data-ttu-id="9fb1b-111">È anche possibile creare criteri di cache basati sul tempo predefiniti usando la classe <xref:System.Net.Cache.RequestCachePolicy> come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9fb1b-111">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fb1b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fb1b-112">See also</span></span>

- [<span data-ttu-id="9fb1b-113">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9fb1b-113">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="9fb1b-114">Criteri cache</span><span class="sxs-lookup"><span data-stu-id="9fb1b-114">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="9fb1b-115">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="9fb1b-115">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="9fb1b-116">Time-Based Cache Policies</span><span class="sxs-lookup"><span data-stu-id="9fb1b-116">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="9fb1b-117">\<elemento> requestCaching (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9fb1b-117">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
