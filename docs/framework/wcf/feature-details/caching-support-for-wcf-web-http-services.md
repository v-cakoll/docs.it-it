---
title: Supporto di memorizzazione nella cache per servizi HTTP Web WCF
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: b6247dd6c178b355fa4de271415b7cac12f6c629
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116675"
---
# <a name="caching-support-for-wcf-web-http-services"></a><span data-ttu-id="cc309-102">Supporto di memorizzazione nella cache per servizi HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="cc309-102">Caching Support for WCF Web HTTP Services</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="cc309-103">consente di utilizzare il meccanismo dichiarativo di memorizzazione nella cache già disponibile in ASP.NET nei servizi HTTP Web WCF.</span><span class="sxs-lookup"><span data-stu-id="cc309-103">enables you to use the declarative caching mechanism already available in ASP.NET in your WCF Web HTTP services.</span></span> <span data-ttu-id="cc309-104">In questo modo è possibile memorizzare nella cache le risposte inviate dalle operazioni del servizio HTTP Web WCF.</span><span class="sxs-lookup"><span data-stu-id="cc309-104">This allows you to cache responses from your WCF Web HTTP service operations.</span></span> <span data-ttu-id="cc309-105">Se un utente invia un'operazione HTTP GET al servizio configurato per la memorizzazione nella cache, ASP.NET restituisce la risposta memorizzata nella cache e il metodo del servizio non viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="cc309-105">When a user sends an HTTP GET to your service that is configured for caching, ASP.NET sends back the cached response and the service method is not called.</span></span> <span data-ttu-id="cc309-106">Se la cache scade, al successivo tentativo di invio di un'operazione HTTP GET da parte dell'utente, viene chiamato il metodo del servizio e la risposta viene nuovamente memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc309-106">When the cache expires, the next time a user sends an HTTP GET, your service method is called and the response is once again cached.</span></span> <span data-ttu-id="cc309-107">Per ulteriori informazioni sulla memorizzazione nella cache ASP.NET, vedere [Cenni preliminari sulla memorizzazione nella cache ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cc309-107">For more information about ASP.NET caching, see [ASP.NET Caching Overview](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).</span></span>  
  
## <a name="basic-web-http-service-caching"></a><span data-ttu-id="cc309-108">Memorizzazione nella cache del servizio HTTP Web di base</span><span class="sxs-lookup"><span data-stu-id="cc309-108">Basic Web HTTP Service Caching</span></span>  

  <span data-ttu-id="cc309-109">Per abilitare la memorizzazione nella cache del servizio HTTP WEB, è innanzitutto necessario abilitare la compatibilità ASP.NET applicando la <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> all'impostazione del servizio <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> o <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span><span class="sxs-lookup"><span data-stu-id="cc309-109">To enable WEB HTTP service caching, you must first enable ASP.NET compatibility by applying the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to the service setting <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> to <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> or <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span></span>  
  
 <span data-ttu-id="cc309-110">.NET Framework 4 introduce un nuovo attributo denominato <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> che consente di specificare un nome di profilo della cache.</span><span class="sxs-lookup"><span data-stu-id="cc309-110">.NET Framework 4 introduces a new attribute called <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> that allows you to specify a cache profile name.</span></span> <span data-ttu-id="cc309-111">L'attributo è applicato a un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="cc309-111">This attribute is applied to a service operation.</span></span> <span data-ttu-id="cc309-112">Nell'esempio seguente <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> viene applicato a un servizio per abilitare la compatibilità ASP.NET e l'operazione `GetCustomer` viene configurata per la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc309-112">The following example applies the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to a service to enable ASP.NET compatibility and configures the `GetCustomer` operation for caching.</span></span> <span data-ttu-id="cc309-113">L'attributo <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> specifica un profilo cache che contiene le impostazioni della cache da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cc309-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> attribute specifies a cache profile that contains the cache settings to be used.</span></span>  
  
```csharp
[ServiceContract] 
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]
public class Service
{
    [WebGet(UriTemplate = "{id}")]
    [AspNetCacheProfile("CacheFor60Seconds")]
    public Customer GetCustomer(string id)
    {
        // ...
    }
}
```  
  
<span data-ttu-id="cc309-114">Attivare anche la modalità di compatibilità ASP.NET nel file Web. config, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cc309-114">Also turn on ASP.NET compatibility mode in the Web.config file as shown in the following example.</span></span>  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> <span data-ttu-id="cc309-115">Se la modalità di compatibilità ASP.NET non è abilitata e viene utilizzato <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cc309-115">If ASP.NET compatibility mode is not turned on and the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is used an exception is thrown.</span></span>  
  
 <span data-ttu-id="cc309-116">Il nome di profilo cache specificato da <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifica un profilo cache aggiunto al file di configurazione Web.config.</span><span class="sxs-lookup"><span data-stu-id="cc309-116">The cache profile name specified by the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifies a cache profile that is added to your Web.config configuration file.</span></span> <span data-ttu-id="cc309-117">Il profilo della cache viene definito con in un <`outputCacheSetting`> elemento, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="cc309-117">The cache profile is defined with in a <`outputCacheSetting`> element as shown in the following configuration example.</span></span>  
  
```xml
<!-- ...  -->
<system.web>  
   <caching>  
      <outputCacheSettings>  
         <outputCacheProfiles>  
            <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable"/>  
         </outputCacheProfiles>  
      </outputCacheSettings>  
   </caching>  
   <!-- ... -->  
</system.web>  
```  
  
 <span data-ttu-id="cc309-118">Si tratta dello stesso elemento di configurazione disponibile per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc309-118">This is the same configuration element that is available to ASP.NET applications.</span></span> <span data-ttu-id="cc309-119">Per ulteriori informazioni sui profili della cache ASP.NET, vedere <xref:System.Web.Configuration.OutputCacheProfile>.</span><span class="sxs-lookup"><span data-stu-id="cc309-119">For more information about ASP.NET cache profiles, see <xref:System.Web.Configuration.OutputCacheProfile>.</span></span> <span data-ttu-id="cc309-120">Per i servizi HTTP Web, gli attributi più importanti del profilo cache sono `cacheDuration` e `varyByParam`.</span><span class="sxs-lookup"><span data-stu-id="cc309-120">For Web HTTP services, the most important attributes in the cache profile are: `cacheDuration` and `varyByParam`.</span></span> <span data-ttu-id="cc309-121">Entrambi gli attributi sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="cc309-121">Both of these attributes are required.</span></span> <span data-ttu-id="cc309-122">`cacheDuration` imposta la quantità di tempo in secondi necessaria per la memorizzazione nella cache di una risposta.</span><span class="sxs-lookup"><span data-stu-id="cc309-122">`cacheDuration` sets the amount of time a response should be cached in seconds.</span></span> <span data-ttu-id="cc309-123">`varyByParam` consente di specificare un parametro della stringa di query utilizzato per memorizzare risposte nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc309-123">`varyByParam` allows you to specify a query string parameter that is used to cache responses.</span></span> <span data-ttu-id="cc309-124">Tutte le richieste effettuate con valori del parametro della stringa di query diversi vengono memorizzate nella cache separatamente.</span><span class="sxs-lookup"><span data-stu-id="cc309-124">All requests made with different query string parameter values are cached separately.</span></span> <span data-ttu-id="cc309-125">Ad esempio, una volta effettuata una richiesta iniziale di `http://MyServer/MyHttpService/MyOperation?param=10`, tutte le richieste successive effettuate con lo stesso URI verrebbero restituite dalla risposta memorizzata nella cache (purché la durata della cache non sia trascorsa).</span><span class="sxs-lookup"><span data-stu-id="cc309-125">For example, once an initial request is made to `http://MyServer/MyHttpService/MyOperation?param=10`, all subsequent requests made with the same URI would be returned the cached response (so long as the cache duration has not elapsed).</span></span> <span data-ttu-id="cc309-126">Le risposte per una richiesta analoga ma con valore diverso per quanto riguarda il parametro della stringa di query vengono memorizzate nella cache separatamente.</span><span class="sxs-lookup"><span data-stu-id="cc309-126">Responses for a similar request that is the same but has a different value for the parameter query string parameter are cached separately.</span></span> <span data-ttu-id="cc309-127">Se non si desidera questo tipo di comportamento di memorizzazione nella cache, impostare `varyByParam` su "none".</span><span class="sxs-lookup"><span data-stu-id="cc309-127">If you do not want this separate caching behavior, set `varyByParam` to "none".</span></span>  
  
## <a name="sql-cache-dependency"></a><span data-ttu-id="cc309-128">Dipendenza dalla cache SQL</span><span class="sxs-lookup"><span data-stu-id="cc309-128">SQL Cache Dependency</span></span>  

  <span data-ttu-id="cc309-129">È inoltre possibile memorizzare nella cache le risposte di un servizio HTTP Web con una dipendenza della cache SQL.</span><span class="sxs-lookup"><span data-stu-id="cc309-129">Web HTTP service responses can also be cached with a SQL cache dependency.</span></span> <span data-ttu-id="cc309-130">Se il servizio HTTP Web WCF dipende da dati archiviati in un database SQL, potrebbe risultare opportuno memorizzare nella cache la risposta del servizio e invalidare la risposta memorizzata nella cache quando i dati nella tabella del database SQL vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="cc309-130">If your WCF Web HTTP service depends on data stored in a SQL database, you may want to cache the service's response and invalidate the cached response when data in the SQL database table changes.</span></span> <span data-ttu-id="cc309-131">Questo comportamento viene completamente configurato all'interno del file Web.config.</span><span class="sxs-lookup"><span data-stu-id="cc309-131">This behavior is configured completely within the Web.config file.</span></span> <span data-ttu-id="cc309-132">Per prima cosa, definire una stringa di connessione nell'elemento <`connectionStrings`>.</span><span class="sxs-lookup"><span data-stu-id="cc309-132">First, define a connection string in the <`connectionStrings`> element.</span></span>  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 <span data-ttu-id="cc309-133">È quindi necessario abilitare la dipendenza della cache SQL all'interno di un elemento <`caching`> all'interno dell'elemento <`system.web`> come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="cc309-133">Then you must enable SQL cache dependency within a <`caching`> element within the <`system.web`> element as shown in the following config example.</span></span>  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>
    </sqlCacheDependency>
    <!-- ... -->
  </caching>
  <!-- ... -->
</system.web>
```  
  
 <span data-ttu-id="cc309-134">In questo caso viene abilitata la dipendenza della cache SQL e viene impostato un tempo di polling di 1000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="cc309-134">Here SQL cache dependency is enabled and a polling time of 1000 milliseconds is set.</span></span> <span data-ttu-id="cc309-135">Ogni volta che scade il tempo di polling, viene verificata la presenza di aggiornamenti nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="cc309-135">Each time the polling time elapses the database table is checked for updates.</span></span> <span data-ttu-id="cc309-136">Se vengono rilevate modifiche, il contenuto della cache viene rimosso e, la volta successiva in cui l'operazione del servizio viene richiamata, viene memorizzata nella cache una nuova risposta.</span><span class="sxs-lookup"><span data-stu-id="cc309-136">If changes are detected the contents of the cache are removed and the next time the service operation is invoked a new response is cached.</span></span> <span data-ttu-id="cc309-137">All'interno dell'elemento <`sqlCacheDependency`> aggiungere i database e fare riferimento alle stringhe di connessione all'interno dell'elemento <`databases`> come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cc309-137">Within the <`sqlCacheDependency`> element add the databases and reference the connection strings within the <`databases`> element as shown in the following example.</span></span>  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>  
    </sqlCacheDependency>  
    <!-- ... -->  
  </caching>  
  <!-- ... -->  
</system.web>  
```  
  
 <span data-ttu-id="cc309-138">Successivamente, è necessario configurare le impostazioni della cache di output all'interno dell'<`caching`> elemento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cc309-138">Next you must configure the output cache settings within the <`caching`> element as shown in the following example.</span></span>  
  
```xml
<system.web>
  <caching>  
    <!-- ...  -->
    <outputCacheSettings>
      <outputCacheProfiles>
        <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable" />
      </outputCacheProfiles>
    </outputCacheSettings>
  </caching>
  <!-- ... -->
</system.web>
```  
  
 <span data-ttu-id="cc309-139">Qui la durata della cache è impostata su 60 secondi, `varyByParam` è impostata su None e `sqlDependency` è impostata su un elenco delimitato da punti e virgola di coppie nome/tabella di database separate da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="cc309-139">Here the cache duration is set to 60 seconds, `varyByParam` is set to none, and `sqlDependency` is set to a semicolon-delimited list of database name/table pairs separated by colons.</span></span> <span data-ttu-id="cc309-140">Se i dati in `MyTable` vengono modificati, la risposta memorizzata nella cache per l'operazione del servizio viene rimossa e, se si richiama l'operazione, una nuova risposta viene generata, memorizzata nella cache e restituita al client.</span><span class="sxs-lookup"><span data-stu-id="cc309-140">When data in `MyTable` is changed the cached response for the service operation is removed and when the operation is invoked a new response is generated (by calling the service operation), cached, and returned to the client.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cc309-141">Per ASP.NET accedere a un database SQL, è necessario usare lo [strumento di registrazione ASP.NET SQL Server](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="cc309-141">For ASP.NET to access a SQL database, you must use the [ASP.NET SQL Server Registration Tool](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90)).</span></span> <span data-ttu-id="cc309-142">È inoltre necessario consentire l'accesso dell'account utente appropriato al database e alla tabella.</span><span class="sxs-lookup"><span data-stu-id="cc309-142">In addition you must allow the appropriate user account access to the database and table.</span></span> <span data-ttu-id="cc309-143">Per ulteriori informazioni, vedere [accesso SQL Server da un'applicazione Web](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cc309-143">For more information, see [Accessing SQL Server from a Web Application](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).</span></span>  
  
## <a name="conditional-http-get-based-caching"></a><span data-ttu-id="cc309-144">Memorizzazione nella cache basata su HTTP GET condizionale</span><span class="sxs-lookup"><span data-stu-id="cc309-144">Conditional HTTP GET Based Caching</span></span>  

  <span data-ttu-id="cc309-145">Negli scenari HTTP Web un HTTP GET condizionale viene spesso usato dai servizi per implementare la memorizzazione nella cache HTTP intelligente, come descritto nella [specifica http](https://www.w3.org/Protocols/rfc2616/rfc2616.html).</span><span class="sxs-lookup"><span data-stu-id="cc309-145">In Web HTTP scenarios a conditional HTTP GET is often used by services to implement intelligent HTTP caching as described in the [HTTP Specification](https://www.w3.org/Protocols/rfc2616/rfc2616.html).</span></span> <span data-ttu-id="cc309-146">A tale scopo, il servizio deve impostare il valore dell'intestazione ETag nella risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc309-146">To do this, the service must set the value of the ETag header in the HTTP response.</span></span> <span data-ttu-id="cc309-147">Deve inoltre verificare l'intestazione If-None-Match nella richiesta HTTP per controllare se una o più delle intestazioni ETag specificate corrisponde all'intestazione ETag corrente.</span><span class="sxs-lookup"><span data-stu-id="cc309-147">It also must check the If-None-Match header in the HTTP request to see whether any of the ETag specified matches the current ETag.</span></span>  
  
 <span data-ttu-id="cc309-148">Per le richieste GET e HEAD, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> utilizza un valore ETag e lo verifica rispetto all'intestazione If-None-Match della richiesta.</span><span class="sxs-lookup"><span data-stu-id="cc309-148">For GET and HEAD requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> takes an ETag value and checks it against the If-None-Match header of the request.</span></span> <span data-ttu-id="cc309-149">Se l'intestazione è presente ed esiste una corrispondenza, viene generata un'<xref:System.ServiceModel.Web.WebFaultException> con un codice di stato HTTP 304 (non modificato) e viene aggiunta un'intestazione ETag alla risposta con l'ETag corrispondente.</span><span class="sxs-lookup"><span data-stu-id="cc309-149">If the header is present and there is a match, a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 304 (Not Modified) is thrown and an ETag header is added to the response with the matching ETag.</span></span>  
  
 <span data-ttu-id="cc309-150">Un overload del metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> utilizza la data di un'ultima modifica e la controlla rispetto all'intestazione If-Modified-Since della richiesta.</span><span class="sxs-lookup"><span data-stu-id="cc309-150">One overload of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method takes a last modified date and checks it against the If-Modified-Since header of the request.</span></span> <span data-ttu-id="cc309-151">Se l'intestazione è presente e la risorsa non è stata ancora modificata, viene generata un'eccezione <xref:System.ServiceModel.Web.WebFaultException> con codice di stato HTTP 304 (non modificato).</span><span class="sxs-lookup"><span data-stu-id="cc309-151">If the header is present and the resource has not been modified since, a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 304 (Not Modified) is thrown.</span></span>  
  
 <span data-ttu-id="cc309-152">Per le richieste PUT, POST e DELETE, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> utilizza il valore ETag corrente di una risorsa.</span><span class="sxs-lookup"><span data-stu-id="cc309-152">For PUT, POST, and DELETE requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> takes the current ETag value of a resource.</span></span> <span data-ttu-id="cc309-153">Se il valore ETag corrente è null, il metodo verifica che il valore dell'intestazione If-None-Match sia "\*".</span><span class="sxs-lookup"><span data-stu-id="cc309-153">If the current ETag value is null, the method checks that the If-None- Match header has a value of "\*".</span></span>  <span data-ttu-id="cc309-154">Se il valore ETag corrente non è un valore predefinito, il metodo controlla il valore ETag corrente rispetto all'intestazione If- Match della richiesta.</span><span class="sxs-lookup"><span data-stu-id="cc309-154">If the current ETag value is not a default value, then the method checks the current ETag value against the If- Match header of the request.</span></span> <span data-ttu-id="cc309-155">In entrambi i casi, il metodo genera un'eccezione <xref:System.ServiceModel.Web.WebFaultException> con codice di stato HTTP 412 (precondizione non riuscita) se l'intestazione prevista non è presente nella richiesta o il relativo valore non soddisfa il controllo condizionale e imposta l'intestazione ETag della risposta sul valore ETag corrente.</span><span class="sxs-lookup"><span data-stu-id="cc309-155">In either case, the method throws a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 412 (Precondition Failed) if the expected header is not present in the request or its value does not satisfy the conditional check and sets the ETag header of the response to the current ETag value.</span></span>  
  
 <span data-ttu-id="cc309-156">Entrambi i metodi `CheckConditional` e il metodo <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> verificano che il valore ETag impostato nell'intestazione della risposta sia valido in base alla specifica HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc309-156">Both the `CheckConditional` methods and the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> method ensures that the ETag value set on the response header is a valid ETag according to the HTTP specification.</span></span> <span data-ttu-id="cc309-157">Ciò include la possibilità di racchiudere il valore ETag tra virgolette, se non già presenti, e di utilizzare i caratteri di escape per eventuali virgolette interne.</span><span class="sxs-lookup"><span data-stu-id="cc309-157">This includes surrounding the ETag value in double quotes if they are not already present and properly escaping any internal double quote characters.</span></span> <span data-ttu-id="cc309-158">Il confronto ETag debole non è supportato.</span><span class="sxs-lookup"><span data-stu-id="cc309-158">Weak ETag comparison is not supported.</span></span>  
  
 <span data-ttu-id="cc309-159">Nell'esempio seguente viene illustrato come utilizzare i metodi.</span><span class="sxs-lookup"><span data-stu-id="cc309-159">The following example shows how to use these methods.</span></span>  
  
```csharp
[WebGet(UriTemplate = "{id}"), Description("Returns the specified customer from customers collection. Returns NotFound if there is no such customer. Supports conditional GET.")]
public Customer GetCustomer(string id)
{
    lock (writeLock)
    {
        // return NotFound if there is no item with the specified id.
        object itemEtag = customerEtags[id];
        if (itemEtag == null)
        {
            throw new WebFaultException(HttpStatusCode.NotFound);
        }
  
        // return NotModified if the client did a conditional GET and the customer item has not changed
        // since when the client last retrieved it
        WebOperationContext.Current.IncomingRequest.CheckConditionalRetrieve((long)itemEtag);
        Customer result = this.customers[id] as Customer;
        
        // set the customer etag before returning the result
        WebOperationContext.Current.OutgoingResponse.SetETag((long)itemEtag);
        return result;
    }
}
```  
  
## <a name="security-considerations"></a><span data-ttu-id="cc309-160">Considerazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="cc309-160">Security Considerations</span></span>  
 <span data-ttu-id="cc309-161">Le risposte a richieste che richiedono autorizzazione non devono essere memorizzate nella cache, perché l'autorizzazione non viene effettuata quando la risposta viene servita dalla cache.</span><span class="sxs-lookup"><span data-stu-id="cc309-161">Requests that require authorization should not have their responses cached, because the authorization is not performed when the response is served from the cache.</span></span>  <span data-ttu-id="cc309-162">La memorizzazione nella cache di tali risposte introdurrebbe una grave vulnerabilità per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cc309-162">Caching such responses would introduce a serious security vulnerability.</span></span>  <span data-ttu-id="cc309-163">In genere, le richiede che richiedono autorizzazione forniscono dati specifici per gli utenti, pertanto la memorizzazione nella cache sul lato server non è vantaggiosa.</span><span class="sxs-lookup"><span data-stu-id="cc309-163">Usually, requests that require authorization provide user-specific data and therefore server-side caching is not even beneficial.</span></span>  <span data-ttu-id="cc309-164">In tali situazioni, risulta più appropriata la memorizzazione nella cache sul lato client o, semplicemente, non eseguire alcuna memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc309-164">In such situations, client-side caching or simply not caching at all will be more appropriate.</span></span>
