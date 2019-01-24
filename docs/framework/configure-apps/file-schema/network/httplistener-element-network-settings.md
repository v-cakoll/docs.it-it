---
title: '&lt;httpListener&gt; (impostazioni di rete)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 896b6633ef4a741b9a7460d8ce3d879253d542da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577698"
---
# <a name="lthttplistenergt-element-network-settings"></a><span data-ttu-id="b0ab9-102">&lt;httpListener&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b0ab9-102">&lt;httpListener&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b0ab9-103">Consente di personalizzare i parametri usati dal <xref:System.Net.HttpListener> classe.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="b0ab9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0ab9-104">\<configuration></span></span>  
<span data-ttu-id="b0ab9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b0ab9-105">\<system.net></span></span>  
<span data-ttu-id="b0ab9-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="b0ab9-106">\<settings></span></span>  
<span data-ttu-id="b0ab9-107">\<httpListener></span><span class="sxs-lookup"><span data-stu-id="b0ab9-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ab9-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0ab9-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="b0ab9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0ab9-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0ab9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b0ab9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0ab9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0ab9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b0ab9-112">Attributes</span></span>  
  
|<span data-ttu-id="b0ab9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b0ab9-113">Attribute</span></span>|<span data-ttu-id="b0ab9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0ab9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0ab9-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="b0ab9-115">unescapeRequestUrl</span></span>|<span data-ttu-id="b0ab9-116">Valore booleano che indica se un <xref:System.Net.HttpListener> istanza utilizza l'URI senza codice di escape non elaborato anziché l'URI convertito.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0ab9-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b0ab9-117">Child Elements</span></span>  
 <span data-ttu-id="b0ab9-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0ab9-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b0ab9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b0ab9-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="b0ab9-120">**Element**</span></span>|<span data-ttu-id="b0ab9-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b0ab9-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b0ab9-122">settings</span><span class="sxs-lookup"><span data-stu-id="b0ab9-122">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="b0ab9-123">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0ab9-124">Note</span><span class="sxs-lookup"><span data-stu-id="b0ab9-124">Remarks</span></span>  
 <span data-ttu-id="b0ab9-125">Il **unescapeRequestUrl** attributo indica se <xref:System.Net.HttpListener> Usa l'URI senza codice di escape non elaborato anziché l'URI convertito in cui vengono convertiti i valori codificati in percentuale e vengono eseguiti altri passaggi di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="b0ab9-126">Quando un <xref:System.Net.HttpListener> istanza riceve una richiesta tramite il `http.sys` servizio, crea un'istanza della stringa URI fornita dal `http.sys`e lo espone come il <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="b0ab9-127">Il `http.sys` servizio espone due stringhe URI richiesta:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
-   <span data-ttu-id="b0ab9-128">URI non elaborato</span><span class="sxs-lookup"><span data-stu-id="b0ab9-128">Raw URI</span></span>  
  
-   <span data-ttu-id="b0ab9-129">URI convertito</span><span class="sxs-lookup"><span data-stu-id="b0ab9-129">Converted URI</span></span>  
  
 <span data-ttu-id="b0ab9-130">L'URI non elaborato è il <xref:System.Uri?displayProperty=nameWithType> fornito nella riga della richiesta di una richiesta HTTP:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="b0ab9-131">L'URI non elaborato fornito dal `http.sys` per è indicato in precedenza, la richiesta di "percorso /".</span><span class="sxs-lookup"><span data-stu-id="b0ab9-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="b0ab9-132">Rappresenta la stringa che segue il verbo HTTP, come è stato inviato in rete.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="b0ab9-133">Il `http.sys` servizio crea un URI convertito dalle informazioni ottenute tramite l'URI fornito nella riga della richiesta HTTP nella richiesta e intestazione Host per determinare il server di origine della richiesta deve essere inoltrato a.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="b0ab9-134">Questa operazione viene eseguita confrontando le informazioni della richiesta con un set di prefissi URI registrati.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="b0ab9-135">La documentazione di HTTP Server SDK fa riferimento a questo URI convertito della struttura di HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="b0ab9-136">Per poter essere in grado di confrontare la richiesta con i prefissi URI registrati, la normalizzazione della richiesta deve essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="b0ab9-137">Nell'esempio precedente l'URI convertito sarà come segue:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="b0ab9-138">Il `http.sys` service combina il <xref:System.Uri.Host%2A?displayProperty=nameWithType> valore della proprietà e la stringa nella riga della richiesta per creare un URI convertito.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="b0ab9-139">È inoltre `http.sys` e il <xref:System.Uri?displayProperty=nameWithType> classe esegue anche le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
-   <span data-ttu-id="b0ab9-140">Escape di annullare la percentuale di tutti i valori codificati.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-140">Un-escapes all percent encoded values.</span></span>  
  
-   <span data-ttu-id="b0ab9-141">Caratteri non ASCII converte codificato in percentuale in una rappresentazione di caratteri UTF-16.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="b0ab9-142">Si noti che i caratteri DBCS/ANSI e UTF-8 sono supportati anche i caratteri Unicode (codifica Unicode utilizzando il formato uXXXX %).</span><span class="sxs-lookup"><span data-stu-id="b0ab9-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
-   <span data-ttu-id="b0ab9-143">Esegue gli altri passaggi di normalizzazione, ad esempio la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="b0ab9-144">Poiché la richiesta non contiene alcuna informazione sulla codifica usata per i valori codificati in percentuale, potrebbe non essere possibile determinare la codifica corretta appena analizzando i valori codificati in percentuale.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="b0ab9-145">Di conseguenza `http.sys` vengono fornite due chiavi del Registro di sistema per la modifica del processo:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="b0ab9-146">Chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="b0ab9-146">Registry Key</span></span>|<span data-ttu-id="b0ab9-147">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="b0ab9-147">Default Value</span></span>|<span data-ttu-id="b0ab9-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0ab9-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="b0ab9-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="b0ab9-149">EnableNonUTF8</span></span>|<span data-ttu-id="b0ab9-150">1</span><span class="sxs-lookup"><span data-stu-id="b0ab9-150">1</span></span>|<span data-ttu-id="b0ab9-151">Se è zero, `http.sys` accetta solo gli URL con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="b0ab9-152">Se diverso da zero, `http.sys` accetta anche un URL con codifica ANSI o con codifica DBCS nelle richieste.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="b0ab9-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="b0ab9-153">FavorUTF8</span></span>|<span data-ttu-id="b0ab9-154">1</span><span class="sxs-lookup"><span data-stu-id="b0ab9-154">1</span></span>|<span data-ttu-id="b0ab9-155">Se diverso da zero, `http.sys` sempre prova a decodificare un URL come UTF-8 per primo; se tale conversione non riesce ed EnableNonUTF8 è diverso da zero, HTTP. sys quindi prova a decodificare come ANSI o DBCS.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="b0ab9-156">Se è zero (ed EnableNonUTF8 è diverso da zero), `http.sys` prova a decodificare come ANSI o DBCS; se non riesce, ritenta una conversione UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="b0ab9-157">Quando <xref:System.Net.HttpListener> riceve una richiesta, Usa l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="b0ab9-158">È necessario per il supporto di caratteri oltre ai caratteri e numeri negli URI.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="b0ab9-159">Un esempio è l'URI seguente, che consente di recuperare informazioni sui clienti per cliente numero "1/3812":</span><span class="sxs-lookup"><span data-stu-id="b0ab9-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="b0ab9-160">Si noti la barra nell'Uri (% 2F) codificati in percentuale.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="b0ab9-161">Ciò è necessario, poiché in questo caso il carattere di barra rappresenta i dati e non un delimitatore di percorso.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="b0ab9-162">Passare la stringa al costruttore Uri causerà l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="b0ab9-163">Suddividendo il percorso in segmenti comporta i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="b0ab9-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="b0ab9-164">Non è questo lo scopo del mittente della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="b0ab9-165">Se il **unescapeRequestUrl** attributo è impostato su **false**, quindi quando il <xref:System.Net.HttpListener> riceve una richiesta, Usa l'URI non elaborato anziché l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="b0ab9-166">Il valore predefinito per il **unescapeRequestUrl** attributo **true**.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="b0ab9-167">Il <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> proprietà può essere utilizzata per ottenere il valore corrente del **unescapeRequestUrl** attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0ab9-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0ab9-168">Example</span></span>  
 <span data-ttu-id="b0ab9-169">Nell'esempio seguente viene illustrato come configurare il <xref:System.Net.HttpListener> classe quando riceve una richiesta per usare l'URI non elaborato anziché l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0ab9-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="b0ab9-170">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="b0ab9-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="b0ab9-171">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b0ab9-171">Namespace</span></span>|<span data-ttu-id="b0ab9-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="b0ab9-172">System.Net</span></span>|  
|<span data-ttu-id="b0ab9-173">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="b0ab9-173">Schema Name</span></span>||  
|<span data-ttu-id="b0ab9-174">File di convalida</span><span class="sxs-lookup"><span data-stu-id="b0ab9-174">Validation File</span></span>||  
|<span data-ttu-id="b0ab9-175">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="b0ab9-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="b0ab9-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0ab9-176">See also</span></span>
- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="b0ab9-177">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="b0ab9-177">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
