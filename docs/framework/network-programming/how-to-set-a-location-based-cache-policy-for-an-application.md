---
title: "Procedura: Impostare criteri di cache basati sulla posizione per un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- explicitly defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
ms.openlocfilehash: 5b4936a54627e6016cabc41954d1a18ae82cdf90
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422467"
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a>Procedura: Impostare criteri di cache basati sulla posizione per un'applicazione
I criteri di cache basati sulla posizione consentono a un'applicazione di definire in modo esplicito il comportamento di memorizzazione nella cache in base alla posizione della risorsa richiesta. Questo argomento illustra l'impostazione dei criteri di cache a livello di codice. Per informazioni sull'impostazione dei criteri per un'applicazione che usa file di configurazione, vedere [Elemento \<requestCaching> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a>Per impostare criteri di cache basati sulla posizione per un'applicazione  
  
1. Creare un oggetto <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
2. Impostare l'oggetto criteri come predefinito per il dominio dell'applicazione.  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a>Per impostare un criterio che prende le risorse richieste da una cache  
  
- È possibile creare un criterio che prende le risorse richieste da una cache, se disponibili, e in caso contrario invia le richieste al server, impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>. Una richiesta può essere soddisfatta da qualsiasi cache tra il client e il server, incluse le cache remote.  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a>Per impostare un criterio che impedisce a qualsiasi cache di fornire risorse  
  
- È possibile creare un criterio che impedisce a qualsiasi cache di fornire le risorse richieste impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>. Questo livello di criteri rimuove la risorsa dalla cache locale se è presente e indica anche alle cache remote di rimuovere la risorsa.  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a>Per impostare un criterio che restituisce le risorse richieste solo se sono nella cache locale  
  
- È possibile creare un criterio che restituisce le risorse richieste solo se sono nella cache locale impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>. Se la risorsa richiesta non è presente nella cache, viene generata un'eccezione <xref:System.Net.WebException>.  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a>Per impostare un criterio che impedisce alla cache locale di fornire risorse  
  
- È possibile creare un criterio che impedisce alla cache locale di fornire le risorse richieste impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>. Se la risorsa richiesta è presente in una cache intermedia e viene riconvalidata correttamente, la cache intermedia può fornire la risorsa richiesta.  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a>Per impostare un criterio che impedisce a qualsiasi cache di fornire le risorse richieste  
  
- È possibile creare un criterio che impedisce a qualsiasi cache di fornire le risorse richieste impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>. La risorsa restituita dal server può essere archiviata nella cache.  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a>Per impostare un criterio che consente a qualsiasi cache di fornire le risorse richieste se la risorsa nel server non è più recente della copia memorizzata nella cache  
  
- È possibile creare un criterio che consente a qualsiasi cache di fornire le risorse richieste se la risorsa nel server non è più recente della copia memorizzata nella cache impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)
- [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [Criteri di cache basati sull'ora](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [Elemento \<requestCaching> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
