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
# <a name="how-to-customize-a-time-based-cache-policy"></a>Procedura: Personalizzare criteri di cache basati sul tempo

Quando si creano criteri di cache basati sul tempo, è possibile personalizzare il comportamento di memorizzazione nella cache specificando i valori per durata massima, validità minima, obsolescenza massima o data di sincronizzazione della cache. L'oggetto <xref:System.Net.Cache.HttpRequestCachePolicy> fornisce più costruttori che consentono di specificare le combinazioni valide di questi valori.

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a>Per creare un criterio di cache basato sul tempo che usa una data di sincronizzazione della cache

Creare criteri di cache basati sul tempo che <xref:System.DateTime> utilizzano <xref:System.Net.Cache.HttpRequestCachePolicy> una data di sincronizzazione della cache passando un oggetto al costruttore:Create a time-based cache policy that uses a cache synchronization date by passing a object to the constructor:

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

L'output è simile al seguente:

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a>Per creare un criterio di cache basato sul tempo con impostazione della validità minima

Creare criteri di cache basati sul tempo basati <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> sull'aggiornamento minimo specificando come valore del `cacheAgeControl` parametro e passando un <xref:System.TimeSpan> oggetto al <xref:System.Net.Cache.HttpRequestCachePolicy> costruttore:

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

Per la chiamata seguente:

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

L'output è:

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a>Per creare un criterio di cache basato sul tempo con impostazione della validità minima e della durata massima

Creare criteri di cache basati sul tempo basati sull'aggiornamento `cacheAgeControl` minimo e sulla <xref:System.TimeSpan> validità <xref:System.Net.Cache.HttpRequestCachePolicy> massima specificando <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> come valore del parametro e passando due oggetti al costruttore, uno per specificare la validità massima delle risorse e un secondo per specificare l'aggiornamento minimo consentito per un oggetto restituito dalla cache:

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

Per la chiamata seguente:
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

L'output è:
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a>Vedere anche

- [Gestione della cache per le applicazioni di rete](cache-management-for-network-applications.md)
- [Criteri cache](cache-policy.md)
- [Criteri di cache basati sulla posizione](location-based-cache-policies.md)
- [Time-Based Cache Policies](time-based-cache-policies.md)
- [\<elemento> requestCaching (impostazioni di rete)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
