---
title: Memorizzazione nella cache in applicazioni .NET Framework
description: Usare la memorizzazione nella cache in applicazioni .NET. Informazioni sulla memorizzazione nella cache dei dati, sulla memorizzazione nella cache in applicazioni ASP.NET o servizi WCF REST e sull'estensione della memorizzazione nella cache in .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- ASP.NET caching
- caching [.NET Framework]
- caching [ASP.NET]
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
ms.openlocfilehash: 9b08a07e9b446c2998150a327dccdc8d0481722a
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309768"
---
# <a name="caching-in-net-framework-applications"></a>Memorizzazione nella cache in applicazioni .NET Framework
La memorizzazione nella cache consente di inserire i dati in memoria per l'accesso rapido. Quando accedono nuovamente ai dati, le applicazioni possono recuperarli dalla cache anziché dall'origine. In questo modo si possono ottenere migliori prestazioni e scalabilità. Inoltre, se si memorizzano i dati nella cache, questi sono accessibili anche quando l'origine dati è temporaneamente non disponibile.  
  
 .NET Framework offre funzionalità di memorizzazione nella cache che è possibile usare per migliorare le prestazioni e la scalabilità delle applicazioni client e server di Windows, tra cui ASP.NET.  
  
> [!NOTE]
> In .NET Framework 3,5 e versioni precedenti, ASP.NET ha fornito un'implementazione della cache in memoria nello <xref:System.Web.Caching> spazio dei nomi. Nelle versioni precedenti del .NET Framework, la memorizzazione nella cache era disponibile solo nello <xref:System.Web> spazio dei nomi e pertanto richiedeva una dipendenza dalle classi ASP.NET. In .NET Framework 4 lo spazio dei nomi <xref:System.Runtime.Caching> contiene API progettate per le applicazioni Web e anche per quelle non Web.  
  
## <a name="caching-data"></a>Memorizzazione di dati nella cache  
 È possibile memorizzare nella cache le informazioni usando le classi dello spazio dei nomi <xref:System.Runtime.Caching>. Le classi di memorizzazione nella cache in questo spazio dei nomi offrono le funzionalità seguenti:  
  
- Tipi astratti che forniscono gli elementi fondamentali per creare implementazioni della cache personalizzate.  
  
- Un'implementazione concreta della cache oggetti in memoria.  
  
 La classe di base astratta di memorizzazione nella cache (<xref:System.Runtime.Caching.ObjectCache>) definisce le attività di memorizzazione nella cache seguenti:  
  
- Creazione e gestione di voci della cache.  
  
- Definizione delle informazioni relative alla scadenza e alla rimozione.  
  
- Attivazione degli eventi generati in risposta a modifiche apportate alle voci della cache.  
  
 La classe <xref:System.Runtime.Caching.MemoryCache> è un'implementazione della cache oggetti in memoria della classe <xref:System.Runtime.Caching.ObjectCache>. È possibile usare la classe <xref:System.Runtime.Caching.MemoryCache> per la maggior parte delle attività di memorizzazione nella cache.  
  
> [!NOTE]
> La classe <xref:System.Runtime.Caching.MemoryCache> è modellata in base all'oggetto cache ASP.NET definito nello spazio dei nomi <xref:System.Web.Caching>. Pertanto, la logica di memorizzazione nella cache interna è simile alla logica fornita nelle versioni precedenti di ASP.NET.  
  
 Per un esempio di come usare la memorizzazione nella cache in un'applicazione WPF, vedere [Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF](../wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md).  
  
## <a name="caching-in-aspnet-applications"></a>Memorizzazione nella cache in applicazioni ASP.NET  
 Le classi di memorizzazione nella cache nello spazio dei nomi <xref:System.Runtime.Caching> offrono funzionalità per memorizzare dati nella cache in ASP.NET.  
  
> [!NOTE]
> Se l'applicazione è destinata a .NET Framework 3,5 o versioni precedenti, è necessario usare le classi di memorizzazione nella cache definite nello <xref:System.Web.Caching> spazio dei nomi. Per altre informazioni, vedere [Cenni preliminari sull'inserimento nella cache in ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
> [!NOTE]
> Quando si sviluppano nuove applicazioni, è consigliabile usare la classe <xref:System.Runtime.Caching.MemoryCache>. L'API disponibile nello spazio dei nomi <xref:System.Runtime.Caching> è analoga a quella dello spazio dei nomi <xref:System.Web.Caching.Cache>. L'API risulterà quindi familiare se si è già usata la memorizzazione nella cache nelle versioni precedenti di ASP.NET. Per un esempio di come usare la memorizzazione nella cache in applicazioni ASP.NET, vedere [Procedura dettagliata: Memorizzazione nella cache dei dati applicazioni in ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100)).  
  
### <a name="output-caching"></a>Memorizzazione dell'output nella cache  
 Per memorizzare manualmente nella cache i dati delle applicazioni, è possibile usare la classe ASP.NET <xref:System.Runtime.Caching.MemoryCache>. ASP.NET supporta anche la memorizzazione dell'output nella cache, permettendo così di inserire in memoria l'output generato da pagine, controlli e risposte HTTP. È possibile configurare la memorizzazione dell'output nella cache in modo dichiarativo, in una pagina Web ASP.NET, oppure usando le impostazioni nel file Web.config. Per altre informazioni, vedere [Elemento outputCache per caching (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228124(v=vs.100)).  
  
 ASP.NET consente di estendere la memorizzazione dell'output nella cache creando provider di cache di output personalizzati. Mediante questi provider, è possibile archiviare il contenuto memorizzato nella cache usando altri dispositivi di archiviazione, come dischi, risorse di archiviazione cloud e motori di cache distribuiti. Per creare un provider di cache di output personalizzato, è necessario creare una classe che deriva dalla classe <xref:System.Web.Caching.OutputCacheProvider> e configurare l'applicazione per l'utilizzo del provider di cache di output personalizzato.  
  
## <a name="caching-in-wcf-rest-services"></a>Memorizzazione nella cache in servizi WCF REST  
 Per i servizi WCF REST, .NET Framework consente di usufruire della memorizzazione dichiarativa dell'output nella cache, disponibile in ASP.NET. In questo modo è possibile memorizzare nella cache le risposte inviate dalle operazioni del servizio WCF REST. Se un utente invia una richiesta HTTP GET a un servizio configurato per la memorizzazione nella cache, ASP.NET restituisce la risposta memorizzata nella cache e il metodo del servizio non viene chiamato. Dopo che la cache è scaduta, al successivo tentativo di invio di una richiesta HTTP GET da parte dell'utente, il metodo del servizio viene chiamato e la risposta viene nuovamente memorizzata nella cache.  
  
 .NET Framework consente inoltre di implementare la memorizzazione condizionale nella cache di HTTP GET. Negli scenari REST una richiesta HTTP GET condizionale viene spesso usata dai servizi per implementare la memorizzazione intelligente nella cache HTTP, come descritto nella [specifica di HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616.html). Per altre informazioni, vedere [Supporto di memorizzazione nella cache per servizi HTTP Web WCF](../wcf/feature-details/caching-support-for-wcf-web-http-services.md).  
  
## <a name="extending-caching-in-the-net-framework"></a>Estensione della memorizzazione nella cache in .NET Framework  
 La memorizzazione nella cache in .NET Framework è stata progettata in modo da supportare l'estendibilità. La classe <xref:System.Runtime.Caching.ObjectCache> consente di creare un'implementazione della cache personalizzata. Questa classe fornisce membri disponibili per tutte le applicazioni gestite, tra cui Windows Form, Windows Presentation Foundation (WPF) e Windows Communications Foundation (WCF). È possibile eseguire questa operazione per creare una classe cache che usa un meccanismo di archiviazione diverso oppure se si vuole usare un controllo granulare per le operazioni della cache.  
  
 Per estendere la memorizzazione nella cache è possibile eseguire queste operazioni:  
  
- Creare una classe personalizzata che deriva dalla classe <xref:System.Runtime.Caching.ObjectCache> e quindi fornire un'implementazione personalizzata della cache nella classe derivata.  
  
- Creare una classe che deriva dalla classe <xref:System.Runtime.Caching.MemoryCache> e personalizzare o estendere la classe derivata. Per un esempio di come eseguire questa operazione, vedere [Caching Application Data by Using Multiple Cache Objects in an ASP.NET Application](https://docs.microsoft.com/archive/blogs/aspnetue/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application) (Memorizzazione nella cache dei dati dell'applicazione mediante più oggetti cache in un'applicazione ASP.NET).  
  
- Creare una classe che deriva dalla classe <xref:System.Web.Caching.OutputCacheProvider> e configurare l'applicazione per l'utilizzo del provider di cache di output personalizzato.  
  
 Per altre informazioni, vedere l'articolo [Extensible Output Caching with ASP.NET 4 (VS 2010 and .NET 4.0 Series)](https://weblogs.asp.net/scottgu/extensible-output-caching-with-asp-net-4-vs-2010-and-net-4-0-series) (Memorizzazione nella cache di output estendibile con ASP.NET 4 - VS 2010 e .NET 4.0) nel blog di Scott Guthrie.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching.MemoryCache>
- [Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF](../wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
- [Procedura dettagliata: Memorizzazione nella cache dei dati applicazioni in ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100))
