---
title: 'Procedura: Personalizzare criteri di cache basati sul tempo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: 1a2ba404e333eeec2a23758c834876d0df5aba81
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040639"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="03f97-102">Procedura: Personalizzare criteri di cache basati sul tempo</span><span class="sxs-lookup"><span data-stu-id="03f97-102">How to: customize a time-based cache policy</span></span>

<span data-ttu-id="03f97-103">Quando si creano criteri di cache basati sul tempo, è possibile personalizzare il comportamento di memorizzazione nella cache specificando i valori per durata massima, validità minima, obsolescenza massima o data di sincronizzazione della cache.</span><span class="sxs-lookup"><span data-stu-id="03f97-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="03f97-104">L'oggetto <xref:System.Net.Cache.HttpRequestCachePolicy> fornisce più costruttori che consentono di specificare le combinazioni valide di questi valori.</span><span class="sxs-lookup"><span data-stu-id="03f97-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="03f97-105">Per creare un criterio di cache basato sul tempo che usa una data di sincronizzazione della cache</span><span class="sxs-lookup"><span data-stu-id="03f97-105">To create a time-based cache policy that uses a cache synchronization date</span></span>

<span data-ttu-id="03f97-106">Creare criteri di cache basati sul tempo che <xref:System.DateTime> utilizzano <xref:System.Net.Cache.HttpRequestCachePolicy> una data di sincronizzazione della cache passando un oggetto al costruttore:Create a time-based cache policy that uses a cache synchronization date by passing a object to the constructor:</span><span class="sxs-lookup"><span data-stu-id="03f97-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)
{
    var policy = new HttpRequestCachePolicy(when);
    Console.WriteLine("When: {0}", when);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy([when])
    Console.WriteLine("When: {0}", [when])
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="03f97-107">L'output è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="03f97-107">The output is similar to the following:</span></span>

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="03f97-108">Per creare un criterio di cache basato sul tempo con impostazione della validità minima</span><span class="sxs-lookup"><span data-stu-id="03f97-108">To create a time-based cache policy that is based on minimum freshness</span></span>

<span data-ttu-id="03f97-109">Creare criteri di cache basati sul tempo basati <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> sull'aggiornamento minimo specificando come valore del `cacheAgeControl` parametro e passando un <xref:System.TimeSpan> oggetto al <xref:System.Net.Cache.HttpRequestCachePolicy> costruttore:</span><span class="sxs-lookup"><span data-stu-id="03f97-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="03f97-110">Per la chiamata seguente:</span><span class="sxs-lookup"><span data-stu-id="03f97-110">For the following invocation:</span></span>

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

<span data-ttu-id="03f97-111">L'output è:</span><span class="sxs-lookup"><span data-stu-id="03f97-111">The output is:</span></span>

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="03f97-112">Per creare un criterio di cache basato sul tempo con impostazione della validità minima e della durata massima</span><span class="sxs-lookup"><span data-stu-id="03f97-112">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>

<span data-ttu-id="03f97-113">Creare criteri di cache basati sul tempo basati sull'aggiornamento `cacheAgeControl` minimo e sulla <xref:System.TimeSpan> validità <xref:System.Net.Cache.HttpRequestCachePolicy> massima specificando <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> come valore del parametro e passando due oggetti al costruttore, uno per specificare la validità massima delle risorse e un secondo per specificare l'aggiornamento minimo consentito per un oggetto restituito dalla cache:</span><span class="sxs-lookup"><span data-stu-id="03f97-113">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache:</span></span>

```csharp
public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="03f97-114">Per la chiamata seguente:</span><span class="sxs-lookup"><span data-stu-id="03f97-114">For the following invocation:</span></span>
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

<span data-ttu-id="03f97-115">L'output è:</span><span class="sxs-lookup"><span data-stu-id="03f97-115">The output is:</span></span>
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="03f97-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03f97-116">See also</span></span>

- [<span data-ttu-id="03f97-117">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="03f97-117">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="03f97-118">Criteri cache</span><span class="sxs-lookup"><span data-stu-id="03f97-118">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="03f97-119">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="03f97-119">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="03f97-120">Time-Based Cache Policies</span><span class="sxs-lookup"><span data-stu-id="03f97-120">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="03f97-121">\<elemento> requestCaching (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="03f97-121">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
