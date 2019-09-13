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
ms.openlocfilehash: 5df070bb2cfef42d60247cad39f2a2f76963bae8
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894739"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a>Procedura: Personalizzare criteri di cache basati sul tempo
Quando si creano criteri di cache basati sul tempo, è possibile personalizzare il comportamento di memorizzazione nella cache specificando i valori per durata massima, validità minima, obsolescenza massima o data di sincronizzazione della cache. L'oggetto <xref:System.Net.Cache.HttpRequestCachePolicy> fornisce più costruttori che consentono di specificare le combinazioni valide di questi valori.  
  
### <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a>Per creare un criterio di cache basato sul tempo che usa una data di sincronizzazione della cache  
  
- Creare un criterio di cache basato sul tempo che usa una data di sincronizzazione della cache passando un oggetto <xref:System.DateTime> al costruttore <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
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
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a>Per creare un criterio di cache basato sul tempo con impostazione della validità minima  
  
- Creare un criterio di cache basato sul tempo con impostazione della validità minima specificando <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> come valore del parametro `cacheAgeControl` e passando un oggetto <xref:System.TimeSpan> al costruttore <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
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
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a>Per creare un criterio di cache basato sul tempo con impostazione della validità minima e della durata massima  
  
- Creare un criterio di cache basato sul tempo con impostazione della validità minima e della durata massima specificando <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> come valore del parametro `cacheAgeControl` e passando due oggetti <xref:System.TimeSpan> al costruttore <xref:System.Net.Cache.HttpRequestCachePolicy>, uno per specificare la durata massima delle risorse e il secondo per specificare la validità minima consentita per un oggetto restituito dalla cache.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
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

- [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)
- [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [Criteri di cache basati sull'ora](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [Elemento \<requestCaching> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
