---
title: Gestione della cache per le applicazioni di rete
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c2b27f3516169ee7b90eaa27fbf22ec02fb638fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391677"
---
# <a name="cache-management-for-network-applications"></a><span data-ttu-id="2df3c-102">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2df3c-102">Cache Management for Network Applications</span></span>
<span data-ttu-id="2df3c-103">Questo argomento e i relativi sottoargomenti descrivono il funzionamento della cache per le risorse ottenute tramite le classi <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> e <xref:System.Net.FtpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="2df3c-103">This topic and its related subtopics describe caching for resources obtained using the <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>  
  
 <span data-ttu-id="2df3c-104">Una cache offre uno spazio di archiviazione temporanea per le risorse richieste da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2df3c-104">A cache provides temporary storage of resources that have been requested by an application.</span></span> <span data-ttu-id="2df3c-105">Se un'applicazione richiede più volte la stessa risorsa, quest'ultima può essere restituita dalla cache, evitando il sovraccarico generato dalla necessità di richiederla nuovamente al server.</span><span class="sxs-lookup"><span data-stu-id="2df3c-105">If an application requests the same resource more than once, the resource can be returned from the cache, avoiding the overhead of re-requesting it from the server.</span></span> <span data-ttu-id="2df3c-106">La memorizzazione nella cache contribuisce a migliorare le prestazioni dell'applicazione riducendo il tempo necessario per ottenere una risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="2df3c-106">Caching can improve application performance by reducing the time required to get a requested resource.</span></span> <span data-ttu-id="2df3c-107">Consente anche di ridurre il traffico di rete limitando il numero di percorsi di andata e ritorno al server.</span><span class="sxs-lookup"><span data-stu-id="2df3c-107">Caching can also decrease network traffic by reducing the number of trips to the server.</span></span> <span data-ttu-id="2df3c-108">Se la memorizzazione nella cache da un lato migliora le prestazioni, dall'altro aumenta il rischio che la risorsa restituita all'applicazione sia obsoleta, ossia non identica a quella che verrebbe inviata dal server se non venisse usata la funzionalità di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="2df3c-108">While caching improves performance, it increases the risk that the resource returned to the application is stale, meaning that it is not identical to the resource that would have been sent by the server if caching were not in use.</span></span>  
  
 <span data-ttu-id="2df3c-109">La memorizzazione nella cache può consentire a utenti o processi non autorizzati di leggere dati riservati.</span><span class="sxs-lookup"><span data-stu-id="2df3c-109">Caching may allow unauthorized users or processes to read sensitive data.</span></span> <span data-ttu-id="2df3c-110">È infatti possibile recuperare una risposta autenticata memorizzata nella cache senza disporre di autorizzazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="2df3c-110">An authenticated response that is cached may be retrieved from the cache without an additional authorization.</span></span> <span data-ttu-id="2df3c-111">Se la memorizzazione nella cache è attivata, modificare il valore della proprietà <xref:System.Net.WebRequest.CachePolicy%2A> in <xref:System.Net.Cache.RequestCacheLevel.BypassCache> o <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> per disattivarla per questo tipo di richiesta.</span><span class="sxs-lookup"><span data-stu-id="2df3c-111">If caching is enabled, change to <xref:System.Net.WebRequest.CachePolicy%2A> to <xref:System.Net.Cache.RequestCacheLevel.BypassCache> or <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> to disable caching for this request.</span></span>  
  
 <span data-ttu-id="2df3c-112">Per ovvi motivi di protezione, la memorizzazione nella cache **non** è consigliata per scenari di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="2df3c-112">Due to security concerns, caching is **not** recommended for middle tier scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2df3c-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="2df3c-113">In This Section</span></span>  
 [<span data-ttu-id="2df3c-114">Criteri di cache</span><span class="sxs-lookup"><span data-stu-id="2df3c-114">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 <span data-ttu-id="2df3c-115">Illustra i concetti di base dei criteri di cache e spiega come definirne uno.</span><span class="sxs-lookup"><span data-stu-id="2df3c-115">Explains what a cache policy is and how to define one.</span></span>  
  
 [<span data-ttu-id="2df3c-116">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="2df3c-116">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 <span data-ttu-id="2df3c-117">Definisce i vari tipi di criteri di cache basati sulla posizione disponibili per le risorse Hypertext Transfer Protocol (http e https).</span><span class="sxs-lookup"><span data-stu-id="2df3c-117">Defines each type of location-based cache policy available for Hypertext Transfer Protocol (http and https) resources.</span></span>  
  
 [<span data-ttu-id="2df3c-118">Criteri di cache basati sull'ora</span><span class="sxs-lookup"><span data-stu-id="2df3c-118">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 <span data-ttu-id="2df3c-119">Descrive i criteri che è possibile usare per personalizzare i criteri di cache basati sull'ora.</span><span class="sxs-lookup"><span data-stu-id="2df3c-119">Describes the criteria that can be used to customize a time-based cache policy.</span></span>  
  
 [<span data-ttu-id="2df3c-120">Configurazione della memorizzazione nella cache per applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2df3c-120">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 <span data-ttu-id="2df3c-121">Descrive come creare a livello di codice criteri di cache e richieste in cui viene usata la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="2df3c-121">Describes how to programmatically create cache policies and requests that use caching.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2df3c-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="2df3c-122">Reference</span></span>  
 <xref:System.Net.Cache>  
 <span data-ttu-id="2df3c-123">Definisce i tipi e le enumerazioni usati per impostare i criteri di cache per le risorse ottenute mediante le classi <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> e <xref:System.Net.FtpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="2df3c-123">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>
