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
ms.openlocfilehash: 6fe569e781b005461ea41e3d6b90859666f9601a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180771"
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="6b0dd-102">Procedura: Impostare criteri di cache basati sulla posizione per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="6b0dd-102">How to: Set a Location-Based Cache Policy for an Application</span></span>
<span data-ttu-id="6b0dd-103">I criteri di cache basati sulla posizione consentono a un'applicazione di definire in modo esplicito il comportamento di memorizzazione nella cache in base alla posizione della risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-103">Location-based cache policies allow an application to explicitly define caching behavior based on the location of the requested resource.</span></span> <span data-ttu-id="6b0dd-104">Questo argomento illustra l'impostazione dei criteri di cache a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-104">This topic demonstrates setting the cache policy programmatically.</span></span> <span data-ttu-id="6b0dd-105">Per informazioni sull'impostazione dei criteri per un'applicazione utilizzando i file di configurazione, vedere [ \<requestCaching> Element (Network Settings)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6b0dd-105">For information on setting the policy for an application using the configuration files, see [\<requestCaching> Element (Network Settings)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="6b0dd-106">Per impostare criteri di cache basati sulla posizione per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="6b0dd-106">To set a location-based cache policy for an application</span></span>  
  
1. <span data-ttu-id="6b0dd-107">Creare un oggetto <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-107">Create a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> object.</span></span>  
  
2. <span data-ttu-id="6b0dd-108">Impostare l'oggetto criteri come predefinito per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-108">Set the policy object as the default for the application domain.</span></span>  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a><span data-ttu-id="6b0dd-109">Per impostare un criterio che prende le risorse richieste da una cache</span><span class="sxs-lookup"><span data-stu-id="6b0dd-109">To set a policy that takes requested resources from a cache</span></span>  
  
- <span data-ttu-id="6b0dd-110">È possibile creare un criterio che prende le risorse richieste da una cache, se disponibili, e in caso contrario invia le richieste al server, impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-110">Create a policy that takes requested resources from a cache if available, and otherwise, sends requests to the server, by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>.</span></span> <span data-ttu-id="6b0dd-111">Una richiesta può essere soddisfatta da qualsiasi cache tra il client e il server, incluse le cache remote.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-111">A request can be fulfilled by any cache between the client and server, including remote caches.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a><span data-ttu-id="6b0dd-112">Per impostare un criterio che impedisce a qualsiasi cache di fornire risorse</span><span class="sxs-lookup"><span data-stu-id="6b0dd-112">To set a policy that prevents any cache from supplying resources</span></span>  
  
- <span data-ttu-id="6b0dd-113">È possibile creare un criterio che impedisce a qualsiasi cache di fornire le risorse richieste impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-113">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>.</span></span> <span data-ttu-id="6b0dd-114">Questo livello di criteri rimuove la risorsa dalla cache locale se è presente e indica anche alle cache remote di rimuovere la risorsa.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-114">This policy level removes the resource from the local cache if it is present and indicates to remote caches that they should also remove the resource.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a><span data-ttu-id="6b0dd-115">Per impostare un criterio che restituisce le risorse richieste solo se sono nella cache locale</span><span class="sxs-lookup"><span data-stu-id="6b0dd-115">To set a policy that returns requested resources only if they are in the local cache</span></span>  
  
- <span data-ttu-id="6b0dd-116">È possibile creare un criterio che restituisce le risorse richieste solo se sono nella cache locale impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-116">Create a policy that returns requested resources only if they are in the local cache by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>.</span></span> <span data-ttu-id="6b0dd-117">Se la risorsa richiesta non è presente nella cache, viene generata un'eccezione <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-117">If the requested resource is not in the cache, a <xref:System.Net.WebException> exception is thrown.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a><span data-ttu-id="6b0dd-118">Per impostare un criterio che impedisce alla cache locale di fornire risorse</span><span class="sxs-lookup"><span data-stu-id="6b0dd-118">To set a policy that prevents the local cache from supplying resources</span></span>  
  
- <span data-ttu-id="6b0dd-119">È possibile creare un criterio che impedisce alla cache locale di fornire le risorse richieste impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-119">Create a policy that prevents the local cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>.</span></span> <span data-ttu-id="6b0dd-120">Se la risorsa richiesta è presente in una cache intermedia e viene riconvalidata correttamente, la cache intermedia può fornire la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-120">If the requested resource is in an intermediate cache and is successfully revalidated, the intermediate cache can supply the requested resource.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a><span data-ttu-id="6b0dd-121">Per impostare un criterio che impedisce a qualsiasi cache di fornire le risorse richieste</span><span class="sxs-lookup"><span data-stu-id="6b0dd-121">To set a policy that prevents any cache from supplying requested resources</span></span>  
  
- <span data-ttu-id="6b0dd-122">È possibile creare un criterio che impedisce a qualsiasi cache di fornire le risorse richieste impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-122">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>.</span></span> <span data-ttu-id="6b0dd-123">La risorsa restituita dal server può essere archiviata nella cache.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-123">The resource returned by the server can be stored in the cache.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a><span data-ttu-id="6b0dd-124">Per impostare un criterio che consente a qualsiasi cache di fornire le risorse richieste se la risorsa nel server non è più recente della copia memorizzata nella cache</span><span class="sxs-lookup"><span data-stu-id="6b0dd-124">To set a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy</span></span>  
  
- <span data-ttu-id="6b0dd-125">È possibile creare un criterio che consente a qualsiasi cache di fornire le risorse richieste se la risorsa nel server non è più recente della copia memorizzata nella cache impostando il livello di cache su <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.</span><span class="sxs-lookup"><span data-stu-id="6b0dd-125">Create a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6b0dd-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b0dd-126">See also</span></span>

- [<span data-ttu-id="6b0dd-127">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="6b0dd-127">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="6b0dd-128">Criteri cache</span><span class="sxs-lookup"><span data-stu-id="6b0dd-128">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="6b0dd-129">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="6b0dd-129">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="6b0dd-130">Time-Based Cache Policies</span><span class="sxs-lookup"><span data-stu-id="6b0dd-130">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="6b0dd-131">\<elemento> requestCaching (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6b0dd-131">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
