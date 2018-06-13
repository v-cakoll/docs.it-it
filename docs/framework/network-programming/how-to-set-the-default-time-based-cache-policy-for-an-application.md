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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 021a13b9124cf54712643e33cbf0ca77ec828b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396672"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="61a7f-102">Procedura: Impostare criteri di cache predefiniti basati sull'ora per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="61a7f-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="61a7f-103">I criteri di cache basati sul tempo predefiniti consentono di definire il comportamento della cache per un'applicazione in base alle intestazioni inviate con la risorsa memorizzata nella cache e al comportamento della cache definito nelle sezioni 13 e 14 del documento RFC 2616, disponibile all'indirizzo [http://www.ietf.org](http://www.ietf.org/). Questo è il comportamento della cache appropriato per la maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="61a7f-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="61a7f-104">Per impostare i criteri automatici predefiniti per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="61a7f-104">To set the default automatic policy for an application</span></span>  
  
1.  <span data-ttu-id="61a7f-105">Creare un oggetto criteri basati sul tempo predefinito.</span><span class="sxs-lookup"><span data-stu-id="61a7f-105">Create a default time-based policy object.</span></span>  
  
2.  <span data-ttu-id="61a7f-106">Impostare l'oggetto criteri come predefinito per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61a7f-106">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61a7f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="61a7f-107">Example</span></span>  
 <span data-ttu-id="61a7f-108">I due esempi in questa sezione producono criteri identici.</span><span class="sxs-lookup"><span data-stu-id="61a7f-108">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="61a7f-109">L'esempio seguente crea un criterio basato sul tempo predefinito e lo imposta come predefinito per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61a7f-109">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
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
  
 <span data-ttu-id="61a7f-110">È anche possibile creare criteri di cache basati sul tempo predefiniti usando la classe <xref:System.Net.Cache.RequestCachePolicy> come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="61a7f-110">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="61a7f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a7f-111">See Also</span></span>  
 [<span data-ttu-id="61a7f-112">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="61a7f-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="61a7f-113">Criteri di cache</span><span class="sxs-lookup"><span data-stu-id="61a7f-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="61a7f-114">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="61a7f-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="61a7f-115">Criteri di cache basati sull'ora</span><span class="sxs-lookup"><span data-stu-id="61a7f-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="61a7f-116">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="61a7f-116">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
