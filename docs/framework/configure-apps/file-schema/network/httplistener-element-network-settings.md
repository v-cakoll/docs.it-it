---
title: Elemento <httpListener> (impostazioni di rete)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: cb24dc7296e2f2f6ea292566330d3d6ae4f25f85
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664131"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="61fd4-102">\<Elemento > httpListener (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="61fd4-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="61fd4-103">Personalizza i <xref:System.Net.HttpListener> parametri utilizzati dalla classe.</span><span class="sxs-lookup"><span data-stu-id="61fd4-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="61fd4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="61fd4-104">\<configuration></span></span>  
<span data-ttu-id="61fd4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="61fd4-105">\<system.net></span></span>  
<span data-ttu-id="61fd4-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="61fd4-106">\<settings></span></span>  
<span data-ttu-id="61fd4-107">\<httpListener></span><span class="sxs-lookup"><span data-stu-id="61fd4-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61fd4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61fd4-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="61fd4-109">Type</span><span class="sxs-lookup"><span data-stu-id="61fd4-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61fd4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61fd4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="61fd4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61fd4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61fd4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="61fd4-112">Attributes</span></span>  
  
|<span data-ttu-id="61fd4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="61fd4-113">Attribute</span></span>|<span data-ttu-id="61fd4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61fd4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61fd4-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="61fd4-115">unescapeRequestUrl</span></span>|<span data-ttu-id="61fd4-116">Valore booleano che indica se un' <xref:System.Net.HttpListener> istanza utilizza l'URI senza escape non elaborato anziché l'URI convertito.</span><span class="sxs-lookup"><span data-stu-id="61fd4-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61fd4-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61fd4-117">Child Elements</span></span>  
 <span data-ttu-id="61fd4-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="61fd4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61fd4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61fd4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="61fd4-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="61fd4-120">**Element**</span></span>|<span data-ttu-id="61fd4-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="61fd4-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="61fd4-122">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="61fd4-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="61fd4-123">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="61fd4-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61fd4-124">Note</span><span class="sxs-lookup"><span data-stu-id="61fd4-124">Remarks</span></span>  
 <span data-ttu-id="61fd4-125">L'attributo **unescapeRequestUrl** indica se <xref:System.Net.HttpListener> utilizza l'URI senza codice di escape non elaborato anziché l'URI convertito in cui vengono convertiti i valori con codifica percentuale e vengono eseguiti altri passaggi di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="61fd4-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="61fd4-126">Quando un' <xref:System.Net.HttpListener> istanza riceve una richiesta tramite il `http.sys` servizio, crea un'istanza della stringa URI fornita da `http.sys`e la espone come <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="61fd4-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="61fd4-127">Il `http.sys` servizio espone due stringhe URI di richiesta:</span><span class="sxs-lookup"><span data-stu-id="61fd4-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="61fd4-128">URI non elaborato</span><span class="sxs-lookup"><span data-stu-id="61fd4-128">Raw URI</span></span>  
  
- <span data-ttu-id="61fd4-129">URI convertito</span><span class="sxs-lookup"><span data-stu-id="61fd4-129">Converted URI</span></span>  
  
 <span data-ttu-id="61fd4-130">L'URI non elaborato è <xref:System.Uri?displayProperty=nameWithType> fornito nella riga della richiesta di una richiesta http:</span><span class="sxs-lookup"><span data-stu-id="61fd4-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="61fd4-131">L'URI non elaborato fornito `http.sys` da per la richiesta indicata in precedenza è "/Path/".</span><span class="sxs-lookup"><span data-stu-id="61fd4-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="61fd4-132">Rappresenta la stringa che segue il verbo HTTP così come è stato inviato in rete.</span><span class="sxs-lookup"><span data-stu-id="61fd4-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="61fd4-133">Il `http.sys` servizio crea un URI convertito dalle informazioni fornite nella richiesta utilizzando l'URI fornito nella riga della richiesta HTTP e l'intestazione host per determinare il server di origine a cui deve essere trasmessa la richiesta.</span><span class="sxs-lookup"><span data-stu-id="61fd4-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="61fd4-134">Questa operazione viene eseguita confrontando le informazioni della richiesta con un set di prefissi URI registrati.</span><span class="sxs-lookup"><span data-stu-id="61fd4-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="61fd4-135">La documentazione relativa all'SDK del server HTTP fa riferimento a questo URI convertito come struttura HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="61fd4-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="61fd4-136">Per poter confrontare la richiesta con i prefissi URI registrati, è necessario eseguire alcune operazioni di normalizzazione per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="61fd4-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="61fd4-137">Per l'esempio sopra l'URI convertito sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="61fd4-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="61fd4-138">Il `http.sys` servizio combina il <xref:System.Uri.Host%2A?displayProperty=nameWithType> valore della proprietà e la stringa nella riga della richiesta per creare un URI convertito.</span><span class="sxs-lookup"><span data-stu-id="61fd4-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="61fd4-139">Inoltre, `http.sys` la <xref:System.Uri?displayProperty=nameWithType> classe esegue anche le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="61fd4-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="61fd4-140">Annulla l'escape di tutti i valori codificati in percentuale.</span><span class="sxs-lookup"><span data-stu-id="61fd4-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="61fd4-141">Converte i caratteri non ASCII con codifica percentuale in una rappresentazione in caratteri UTF-16.</span><span class="sxs-lookup"><span data-stu-id="61fd4-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="61fd4-142">Si noti che i caratteri UTF-8 e ANSI/DBCS sono supportati e i caratteri Unicode (codifica Unicode con il formato% uXXXX).</span><span class="sxs-lookup"><span data-stu-id="61fd4-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="61fd4-143">Esegue altri passaggi di normalizzazione, come la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="61fd4-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="61fd4-144">Poiché la richiesta non contiene informazioni sulla codifica utilizzata per i valori con codifica percentuale, potrebbe non essere possibile determinare la codifica corretta semplicemente analizzando i valori con codifica percentuale.</span><span class="sxs-lookup"><span data-stu-id="61fd4-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="61fd4-145">Fornisce `http.sys` pertanto due chiavi del registro di sistema per modificare il processo:</span><span class="sxs-lookup"><span data-stu-id="61fd4-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="61fd4-146">Chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="61fd4-146">Registry Key</span></span>|<span data-ttu-id="61fd4-147">Default Value</span><span class="sxs-lookup"><span data-stu-id="61fd4-147">Default Value</span></span>|<span data-ttu-id="61fd4-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61fd4-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="61fd4-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="61fd4-149">EnableNonUTF8</span></span>|<span data-ttu-id="61fd4-150">1</span><span class="sxs-lookup"><span data-stu-id="61fd4-150">1</span></span>|<span data-ttu-id="61fd4-151">Se è zero `http.sys` , accetta solo URL con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="61fd4-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="61fd4-152">Se diverso da zero, `http.sys` accetta anche URL con codifica ANSI o DBCS nelle richieste.</span><span class="sxs-lookup"><span data-stu-id="61fd4-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="61fd4-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="61fd4-153">FavorUTF8</span></span>|<span data-ttu-id="61fd4-154">1</span><span class="sxs-lookup"><span data-stu-id="61fd4-154">1</span></span>|<span data-ttu-id="61fd4-155">Se diverso da zero, `http.sys` tenta sempre di decodificare un URL come UTF-8. se la conversione ha esito negativo e EnableNonUTF8 è diverso da zero, http. sys tenta di decodificarlo come ANSI o DBCS.</span><span class="sxs-lookup"><span data-stu-id="61fd4-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="61fd4-156">Se zero (e EnableNonUTF8 è diverso da zero), `http.sys` tenta di decodificarlo come ANSI o DBCS; se l'operazione ha esito negativo, tenta una conversione UTF-8.</span><span class="sxs-lookup"><span data-stu-id="61fd4-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="61fd4-157">Quando <xref:System.Net.HttpListener> riceve una richiesta, usa l'URI convertito da `http.sys` come input per la <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="61fd4-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="61fd4-158">È necessario supportare i caratteri oltre ai caratteri e ai numeri negli URI.</span><span class="sxs-lookup"><span data-stu-id="61fd4-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="61fd4-159">Un esempio è l'URI seguente, che viene usato per recuperare le informazioni sul cliente per il numero cliente "1/3812":</span><span class="sxs-lookup"><span data-stu-id="61fd4-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="61fd4-160">Prendere nota della barra codificata in percentuale nell'URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="61fd4-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="61fd4-161">Questa operazione è necessaria, poiché in questo caso il carattere barra rappresenta i dati e non un delimitatore di percorso.</span><span class="sxs-lookup"><span data-stu-id="61fd4-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="61fd4-162">Passando la stringa al costruttore URI si otterrà l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="61fd4-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="61fd4-163">Suddividendo il percorso nei segmenti si verificheranno gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="61fd4-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="61fd4-164">Non si tratta dello scopo del mittente della richiesta.</span><span class="sxs-lookup"><span data-stu-id="61fd4-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="61fd4-165">Se l'attributo **unescapeRequestUrl** è impostato su **false**, quando <xref:System.Net.HttpListener> riceve una richiesta, usa l'URI non elaborato anziché l'URI convertito da `http.sys` come input per la <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="61fd4-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="61fd4-166">Il valore predefinito per l'attributo **unescapeRequestUrl** è **true**.</span><span class="sxs-lookup"><span data-stu-id="61fd4-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="61fd4-167">È <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> possibile usare la proprietà per ottenere il valore corrente dell'attributo **unescapeRequestUrl** dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="61fd4-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61fd4-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="61fd4-168">Example</span></span>  
 <span data-ttu-id="61fd4-169">Nell'esempio seguente viene illustrato come configurare la <xref:System.Net.HttpListener> classe quando viene ricevuta una richiesta di utilizzo dell'URI non elaborato anziché dell'URI convertito da `http.sys` come input per la <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="61fd4-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="61fd4-170">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="61fd4-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="61fd4-171">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="61fd4-171">Namespace</span></span>|<span data-ttu-id="61fd4-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="61fd4-172">System.Net</span></span>|  
|<span data-ttu-id="61fd4-173">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="61fd4-173">Schema Name</span></span>||  
|<span data-ttu-id="61fd4-174">File di convalida</span><span class="sxs-lookup"><span data-stu-id="61fd4-174">Validation File</span></span>||  
|<span data-ttu-id="61fd4-175">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="61fd4-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="61fd4-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61fd4-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="61fd4-177">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="61fd4-177">Network Settings Schema</span></span>](index.md)
