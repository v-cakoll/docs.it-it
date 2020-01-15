---
title: Scelta di un filtro
ms.date: 03/30/2017
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
ms.openlocfilehash: 282f6e9e2bc986feee0d1825ee9d87217d453e50
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964808"
---
# <a name="choosing-a-filter"></a><span data-ttu-id="d5153-102">Scelta di un filtro</span><span class="sxs-lookup"><span data-stu-id="d5153-102">Choosing a Filter</span></span>
<span data-ttu-id="d5153-103">Quando si configura il servizio di routing, è importante selezionare i filtri messaggi corretti e configurarli per consentire l'individuazione di corrispondenze esatte con i messaggi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="d5153-103">When configuring the Routing Service, it is important to select correct message filters and configure them to allow you to make exact matches against the messages you receive.</span></span> <span data-ttu-id="d5153-104">Se i filtri selezionati non sono sufficientemente precisi o non sono configurati correttamente, i messaggi vengono indirizzati in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="d5153-104">If the filters you select are overly broad in their matches or are incorrectly configured, messages are routed incorrectly.</span></span> <span data-ttu-id="d5153-105">Se i filtri sono troppo restrittivi, è possibile che non vengano individuate route valide disponibili per alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="d5153-105">If the filters are too restrictive, you may not have any valid routes available for some of your messages.</span></span>

## <a name="filter-types"></a><span data-ttu-id="d5153-106">Tipi di filtro</span><span class="sxs-lookup"><span data-stu-id="d5153-106">Filter Types</span></span>

<span data-ttu-id="d5153-107">Se si selezionano filtri utilizzati dal servizio di routing, è importante comprenderne il funzionamento ed essere a conoscenza delle informazioni disponibili all'interno dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d5153-107">When selecting the filters that are used by the Routing Service, it is important that you understand how each filter works as well as what information is available as part of the incoming messages.</span></span> <span data-ttu-id="d5153-108">Se ad esempio tutti i messaggi vengono ricevuti sullo stesso endpoint, i filtri Address e EndpointName non sono utili perché tutti i messaggi corrispondono a questi filtri.</span><span class="sxs-lookup"><span data-stu-id="d5153-108">For instance, if all messages are received over the same endpoint, the Address and EndpointName filters are not useful because all messages match these filters.</span></span>

### <a name="action"></a><span data-ttu-id="d5153-109">Azione</span><span class="sxs-lookup"><span data-stu-id="d5153-109">Action</span></span>

<span data-ttu-id="d5153-110">Il filtro Action controlla la proprietà <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5153-110">The Action filter inspects the <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> property.</span></span> <span data-ttu-id="d5153-111">Se il contenuto dell'intestazione Action nel messaggio corrisponde al valore dei dati specificato nella configurazione del filtro, viene restituito `true`.</span><span class="sxs-lookup"><span data-stu-id="d5153-111">If the contents of the Action header in the message match the filter data value specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="d5153-112">Nell'esempio seguente viene definito un `FilterElement` che utilizza il filtro Action per trovare la corrispondenza con i messaggi con un'intestazione Action contenente un valore `http://namespace/contract/operation/`.</span><span class="sxs-lookup"><span data-stu-id="d5153-112">The following example defines a `FilterElement` that uses the Action filter to match messages with an action header that contains a value of `http://namespace/contract/operation/`.</span></span>

```xml
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />
```

```csharp
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
```

<span data-ttu-id="d5153-113">Questo filtro deve essere utilizzato per il routing dei messaggi contenenti un'intestazione Action univoca.</span><span class="sxs-lookup"><span data-stu-id="d5153-113">This filter should be used when routing messages that contain a unique Action header.</span></span>

### <a name="endpointaddress"></a><span data-ttu-id="d5153-114">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="d5153-114">EndpointAddress</span></span>

<span data-ttu-id="d5153-115">Il filtro EndpointAddress controlla il valore EndpointAddress indicante l'indirizzo di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d5153-115">The EndpointAddress filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="d5153-116">Se l'indirizzo a cui arriva il messaggio corrisponde esattamente all'indirizzo specificato nella configurazione del filtro, quest'ultimo restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="d5153-116">If the address that the message arrives at exactly matches the filter address specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="d5153-117">Nell'esempio seguente viene definito un `FilterElement` che utilizza il filtro degli indirizzi per trovare la corrispondenza con qualsiasi messaggio indirizzato a "http://\<hostname >/vdir/s.svc/b".</span><span class="sxs-lookup"><span data-stu-id="d5153-117">The following example defines a `FilterElement` that uses the Address filter to match any messages addressed to "http://\<hostname>/vdir/s.svc/b".</span></span>

```xml
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> <span data-ttu-id="d5153-118">È importante notare che la parte del nome host di un indirizzo può differire a seconda che il client utilizzi il nome di dominio completo, il nome NetBIOS, l'indirizzo IP o un altro nome.</span><span class="sxs-lookup"><span data-stu-id="d5153-118">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="d5153-119">Poiché valori diversi possono fare riferimento allo stesso host, il comportamento predefinito per questo confronto non prevede l'utilizzo della parte del nome host dell'indirizzo per individuare le corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="d5153-119">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>
>
> <span data-ttu-id="d5153-120">È possibile modificare questo comportamento per consentire la valutazione del nome host nel confronto quando si configura il servizio di routing a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d5153-120">This behavior can be modified to allow the comparison to evaluate the host name when configuring the Routing Service programmatically.</span></span>

<span data-ttu-id="d5153-121">È consigliabile utilizzare questo filtro quando i messaggi in ingresso vengono indirizzati a un indirizzo univoco.</span><span class="sxs-lookup"><span data-stu-id="d5153-121">This filter should be used when the incoming messages are addressed to a unique address.</span></span>

### <a name="endpointaddressprefix"></a><span data-ttu-id="d5153-122">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="d5153-122">EndpointAddressPrefix</span></span>

<span data-ttu-id="d5153-123">Il filtro EndpointAddressPrefix è analogo al filtro EndpointAddress.</span><span class="sxs-lookup"><span data-stu-id="d5153-123">The EndpointAddressPrefix filter is similar to the EndpointAddress filter.</span></span> <span data-ttu-id="d5153-124">Il filtro EndpointAddressPrefix controlla il valore EndpointAddress indicante l'indirizzo di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d5153-124">The EndpointAddressPrefix filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="d5153-125">Tuttavia, il filtro EndpointAddressPrefix viene utilizzato come un carattere jolly che individua le corrispondenze con gli indirizzi che iniziano con il valore specificato nella configurazione del filtro.</span><span class="sxs-lookup"><span data-stu-id="d5153-125">However the EndpointAddressPrefix filter acts as a wildcard by matching addresses that begin with the value specified in the filter configuration.</span></span> <span data-ttu-id="d5153-126">Nell'esempio seguente viene definito un `FilterElement` che utilizza il filtro EndpointAddressPrefix per trovare la corrispondenza con tutti i messaggi destinati a `http://<hostname>/vdir*`.</span><span class="sxs-lookup"><span data-stu-id="d5153-126">The following example defines a `FilterElement` that uses the EndpointAddressPrefix filter to match any messages addressed to `http://<hostname>/vdir*`.</span></span>

```xml
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />
```

```csharp
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> <span data-ttu-id="d5153-127">È importante notare che la parte del nome host di un indirizzo può differire a seconda che il client utilizzi il nome di dominio completo, il nome NetBIOS, l'indirizzo IP o un altro nome.</span><span class="sxs-lookup"><span data-stu-id="d5153-127">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="d5153-128">Poiché valori diversi possono fare riferimento allo stesso host, il comportamento predefinito per questo confronto non prevede l'utilizzo della parte del nome host dell'indirizzo per individuare le corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="d5153-128">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>

<span data-ttu-id="d5153-129">È consigliabile utilizzare questo filtro per il routing dei messaggi in ingresso che condividono un prefisso di indirizzo comune.</span><span class="sxs-lookup"><span data-stu-id="d5153-129">This filter should be used when routing incoming messages that share a common address prefix.</span></span>

### <a name="and"></a><span data-ttu-id="d5153-130">AND</span><span class="sxs-lookup"><span data-stu-id="d5153-130">AND</span></span>

<span data-ttu-id="d5153-131">Il filtro AND non applica direttamente il filtro in base a un valore all'interno di un messaggio, ma consente di combinare due altri filtri per creare una condizione `AND` in cui entrambi i filtri devono corrispondere al messaggio affinché venga restituito `true`.</span><span class="sxs-lookup"><span data-stu-id="d5153-131">The AND filter does not directly filter on a value within a message, but allows you to combine two other filters to create an `AND` condition where both filters must match the message before the AND filter evaluates to `true`.</span></span> <span data-ttu-id="d5153-132">In questo modo è possibile creare filtri complessi che prevedono la corrispondenza dei messaggi con tutti i sottofiltri.</span><span class="sxs-lookup"><span data-stu-id="d5153-132">This allows you to create complex filters that only match if all the sub-filters match.</span></span> <span data-ttu-id="d5153-133">Nell'esempio seguente vengono definiti un filtro indirizzo e un filtro Action, quindi viene definito un filtro AND che valuta un messaggio in base sia al filtro indirizzo sia a quello azione.</span><span class="sxs-lookup"><span data-stu-id="d5153-133">The following example defines an address filter and an action filter, and then defines an AND filter that evaluates a message against both the address and action filters.</span></span> <span data-ttu-id="d5153-134">Se entrambi i filtri corrispondono, il filtro AND restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="d5153-134">If both the address and the action filters match, then the AND filter returns `true`.</span></span>

```xml
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);
```

<span data-ttu-id="d5153-135">È consigliabile utilizzare questo filtro quando è necessario combinare la logica di più filtri per determinare quando si verifica una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="d5153-135">This filter should be used when you must combine the logic from multiple filters to determine when a match should be made.</span></span> <span data-ttu-id="d5153-136">Se ad esempio si dispone di più destinazioni che devono ricevere solo determinate combinazioni di azioni e messaggi a specifici indirizzi, è possibile utilizzare un filtro AND per combinare i filtri indirizzo e azione necessari.</span><span class="sxs-lookup"><span data-stu-id="d5153-136">For example, if you have multiple destinations that must receive only certain combinations of actions and messages to particular addresses, you can use an AND filter to combine the necessary Action and Address filters.</span></span>

### <a name="custom"></a><span data-ttu-id="d5153-137">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="d5153-137">Custom</span></span>

<span data-ttu-id="d5153-138">Quando si seleziona il tipo di filtro personalizzato, è necessario specificare un valore customType che contenga il tipo di assembly che contiene l'implementazione di **MessageFilter** da utilizzare per il filtro.</span><span class="sxs-lookup"><span data-stu-id="d5153-138">When selecting the Custom filter type, you must provide a customType value that contains the type of the assembly that contains the **MessageFilter** implementation to be used for this filter.</span></span> <span data-ttu-id="d5153-139">Inoltre, filterData deve contenere qualsiasi valore necessario per la valutazione dei messaggi da parte del filtro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d5153-139">Additionally, filterData must contain any values that the custom filter may require in its evaluation of messages.</span></span> <span data-ttu-id="d5153-140">Nell'esempio seguente viene definito un elemento `FilterElement` che utilizza l'implementazione di MessageFilter `CustomAssembly.MyCustomMsgFilter`.</span><span class="sxs-lookup"><span data-stu-id="d5153-140">The following example defines a `FilterElement` that uses the `CustomAssembly.MyCustomMsgFilter` MessageFilter implementation.</span></span>

```xml
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />
```

```csharp
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");
```

<span data-ttu-id="d5153-141">Se è necessario eseguire una logica di corrispondenza personalizzata per un messaggio non incluso nei filtri forniti con [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], è necessario creare un filtro personalizzato che è un'implementazione della classe **MessageFilter** .</span><span class="sxs-lookup"><span data-stu-id="d5153-141">If you need to perform custom matching logic against a message that is not covered by the filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], you must create a custom filter that is an implementation of the **MessageFilter** class.</span></span> <span data-ttu-id="d5153-142">È ad esempio possibile creare un filtro personalizzato che confronta un campo nel messaggio in ingresso rispetto a un elenco di valori noti specificato nella configurazione del filtro o che esegue l'hashing di un messaggio e quindi esamina il valore per determinare se il filtro deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d5153-142">For example, you might create a custom filter that compares a field in the incoming message against a list of known values given to the filter as configuration, or that hashes a particular message element and then examines that value to determine whether the filter should return `true` or `false`.</span></span>

### <a name="endpointname"></a><span data-ttu-id="d5153-143">EndpointName</span><span class="sxs-lookup"><span data-stu-id="d5153-143">EndpointName</span></span>

<span data-ttu-id="d5153-144">Il filtro EndpointName controlla il nome dell'endpoint che ha ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="d5153-144">The EndpointName filter inspects the name of the endpoint that received the message.</span></span> <span data-ttu-id="d5153-145">Nell'esempio seguente viene definito un `FilterElement` che utilizza il filtro EndpointName per indirizzare i messaggi ricevuti su "SvcEndpoint".</span><span class="sxs-lookup"><span data-stu-id="d5153-145">The following example defines a `FilterElement` that uses the EndpointName filter to route messages received on the "SvcEndpoint".</span></span>

```xml
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />
```

```csharp
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");
```

<span data-ttu-id="d5153-146">Questo filtro è utile quando il servizio di routing espone più endpoint servizio denominati.</span><span class="sxs-lookup"><span data-stu-id="d5153-146">This filter is useful when the Routing Service exposes more than one named service endpoint.</span></span> <span data-ttu-id="d5153-147">È ad esempio possibile esporre due endpoint che il servizio di routing utilizza per ricevere messaggi; uno per i clienti prioritari per i quali è necessaria elaborazione in tempo reale dei messaggi, l'altro per la ricezione dei messaggi non dipendenti dal tempo.</span><span class="sxs-lookup"><span data-stu-id="d5153-147">For example, you might expose two endpoints that the Routing Service uses to receive messages; one is used by priority customers who require real-time processing of their messages, while the other endpoint receives messages that are not time sensitive.</span></span>

<span data-ttu-id="d5153-148">Sebbene sia spesso possibile utilizzare la corrispondenza dell'indirizzo completa per determinare l'endpoint di ricezione di un messaggio, l'utilizzo del nome dell'endpoint risulta più pratico ed è meno soggetto a errori, in particolare quando si configura un servizio di routing con un file di configurazione (in cui i nomi degli endpoint sono un attributo obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="d5153-148">While you can often use full address matching to determine which endpoint a message was received on, using the defined endpoint name instead is a convenient shortcut that is often less error prone, especially when configuring a Routing Service using a configuration file (where endpoint names are a required attribute).</span></span>

### <a name="matchall"></a><span data-ttu-id="d5153-149">MatchAll</span><span class="sxs-lookup"><span data-stu-id="d5153-149">MatchAll</span></span>

<span data-ttu-id="d5153-150">Il filtro MatchAll corrisponde a tutti i messaggi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="d5153-150">The MatchAll filter matches any received message.</span></span> <span data-ttu-id="d5153-151">È utile se è necessario indirizzare sempre tutti i messaggi ricevuti a un endpoint specifico, ad esempio un servizio di registrazione che archivia una copia di tutti i messaggi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="d5153-151">It is useful if you must always route all received messages to a specific endpoint, such as a logging service that stores a copy of all received messages.</span></span> <span data-ttu-id="d5153-152">Nell'esempio seguente viene definito un elemento `FilterElement` che utilizza il filtro MatchAll.</span><span class="sxs-lookup"><span data-stu-id="d5153-152">The following example defines a `FilterElement` that uses the MatchAll filter.</span></span>

```xml
<filter name="matchAll1" filterType="MatchAll" />
```

```csharp
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();
```

### <a name="xpath"></a><span data-ttu-id="d5153-153">XPath</span><span class="sxs-lookup"><span data-stu-id="d5153-153">XPath</span></span>

<span data-ttu-id="d5153-154">Il filtro XPath consente di specificare una query XPath utilizzata per controllare un elemento specifico all'interno del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d5153-154">The XPath filter allows you to specify an XPath query that is used to inspect a specific element within the message.</span></span> <span data-ttu-id="d5153-155">L'applicazione di filtri XPath rappresenta un'opzione particolarmente efficace per consentire il controllo diretto di qualsiasi voce indirizzabile XML nel messaggio, tuttavia richiede una conoscenza specifica della struttura dei messaggi in ricezione.</span><span class="sxs-lookup"><span data-stu-id="d5153-155">XPath filtering is a powerful filtering option that allows you to directly inspect any XML addressable entry within the message; however it requires that you have specific knowledge of the structure of the messages that you are receiving.</span></span> <span data-ttu-id="d5153-156">Nell'esempio seguente viene definito un `FilterElement` che utilizza il filtro XPath per esaminare il messaggio per un elemento denominato "element" nello spazio dei nomi a cui fa riferimento il prefisso dello spazio dei nomi "NS".</span><span class="sxs-lookup"><span data-stu-id="d5153-156">The following example defines a `FilterElement` that uses the XPath filter to inspect the message for an element named "element" within the namespace referenced by the "ns" namespace prefix.</span></span>

```xml
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />
```

```csharp
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");
```

<span data-ttu-id="d5153-157">Questo filtro è utile se si è certi che i messaggi in ricezione contengono un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="d5153-157">This filter is useful if you know that the messages you are receiving contain a specific value.</span></span> <span data-ttu-id="d5153-158">Se ad esempio si ospitano due versioni dello stesso servizio e si sa che messaggi indirizzati alla versione più recente del servizio contengono un valore univoco in un'intestazione personalizzata, è possibile creare un filtro che utilizza XPath per passare a questa intestazione e confrontare il valore presente nell'intestazione con un altro specificato nella configurazione del filtro per determinare le corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="d5153-158">For example, if you are hosting two versions of the same service and you know that messages addressed to the newer version of the service contain a unique value in a custom header, you can create a filter that uses XPath to navigate to this header and compares the value present in the header to another given in the filter configuration to determine if the filter matches.</span></span>

<span data-ttu-id="d5153-159">Poiché le query XPath spesso contengono spazi dei nomi univoci, che spesso sono valori stringa lunghi o complessi, il filtro XPath consente di utilizzare la tabella degli spazi dei nomi per definire prefissi univoci per gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d5153-159">Because XPath queries often contain unique namespaces, which are often lengthy or complex string values, the XPath filter allows you to use the namespace table to define unique prefixes for your namespaces.</span></span> <span data-ttu-id="d5153-160">Per ulteriori informazioni sulla tabella dello spazio dei nomi, vedere [filtri messaggi](../../../../docs/framework/wcf/feature-details/message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="d5153-160">For more information about the namespace table, see [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>

<span data-ttu-id="d5153-161">Per ulteriori informazioni sulla progettazione di query XPath, vedere [sintassi XPath](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d5153-161">For more information about designing XPath queries, see [XPath Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5153-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5153-162">See also</span></span>

- [<span data-ttu-id="d5153-163">Filtri per messaggi</span><span class="sxs-lookup"><span data-stu-id="d5153-163">Message Filters</span></span>](../../../../docs/framework/wcf/feature-details/message-filters.md)
- [<span data-ttu-id="d5153-164">Procedura: Usare filtri</span><span class="sxs-lookup"><span data-stu-id="d5153-164">How To: Use Filters</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-filters.md)
