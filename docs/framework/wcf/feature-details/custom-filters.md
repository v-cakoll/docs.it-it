---
title: Filtri personalizzati
ms.date: 03/30/2017
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
ms.openlocfilehash: ae020173544372c3ce097c8ac57e53f3fde37514
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185215"
---
# <a name="custom-filters"></a><span data-ttu-id="b4c35-102">Filtri personalizzati</span><span class="sxs-lookup"><span data-stu-id="b4c35-102">Custom Filters</span></span>
<span data-ttu-id="b4c35-103">I filtri personalizzati consentono di definire la logica corrispondente che non è possibile conseguire utilizzando i filtri messaggi forniti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b4c35-103">Custom filters allow you to define matching logic that cannot be accomplished using the system-provided message filters.</span></span> <span data-ttu-id="b4c35-104">È ad esempio possibile creare un filtro personalizzato che esegue l'hash di un particolare elemento del messaggio, quindi esamina il valore per determinare se il filtro debba restituire True o False.</span><span class="sxs-lookup"><span data-stu-id="b4c35-104">For example, you might create a custom filter that hashes a particular message element and then examines the value to determine whether the filter should return true or false.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="b4c35-105">Implementazione</span><span class="sxs-lookup"><span data-stu-id="b4c35-105">Implementation</span></span>  
 <span data-ttu-id="b4c35-106">Un filtro personalizzato rappresenta un'implementazione della classe di base astratta <xref:System.ServiceModel.Dispatcher.MessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="b4c35-106">A custom filter is an implementation of the <xref:System.ServiceModel.Dispatcher.MessageFilter> abstract base class.</span></span> <span data-ttu-id="b4c35-107">In caso di implementazione del filtro personalizzato, il costruttore può facoltativamente accettare un solo parametro stringa.</span><span class="sxs-lookup"><span data-stu-id="b4c35-107">When implementing your custom filter, the constructor can optionally accept a single string parameter.</span></span> <span data-ttu-id="b4c35-108">Tale parametro contiene le informazioni di configurazione passate al costruttore MessageFilter per fornire qualsiasi valore o configurazione necessaria al filtro al runtime per eseguire corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="b4c35-108">This parameter contains the configuration information that is passed to the MessageFilter constructor in order to provide any values or configuration that the filter needs at runtime in order to perform matches.</span></span> <span data-ttu-id="b4c35-109">Potrebbe ad esempio essere utilizzato per fornire un valore che il filtro cerca all'interno del messaggio valutato.</span><span class="sxs-lookup"><span data-stu-id="b4c35-109">For example, this might be used to provide a value that the filter looks for within the message being evaluated.</span></span> <span data-ttu-id="b4c35-110">Nell'esempio seguente viene illustrata un'implementazione di base di un filtro messaggi personalizzato che accetta un parametro stringa:</span><span class="sxs-lookup"><span data-stu-id="b4c35-110">The following example demonstrates a basic implementation of a custom message filter that accepts a string parameter:</span></span>  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="b4c35-111">In un'implementazione effettiva, il Match metodo(i) contiene la logica che esaminerà il messaggio per determinare se questo filtro messaggi deve restituire **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="b4c35-111">In an actual implementation, the Match method(s) contains logic that will examine the message to determine if this message filter should return **true** or **false**.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="b4c35-112">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="b4c35-112">Performance</span></span>  
 <span data-ttu-id="b4c35-113">Quando si implementa un filtro personalizzato, è importante considerare la durata di tempo massima richiesta per il completamento della valutazione di un messaggio da parte del filtro.</span><span class="sxs-lookup"><span data-stu-id="b4c35-113">When implementing a custom filter, it is important to take into consideration the maximum length of time required for the filter to complete the evaluation of a message.</span></span> <span data-ttu-id="b4c35-114">Poiché un messaggio può essere valutato rispetto a più filtri prima che venga individuata una corrispondenza, è importante assicurarsi che non si verifichi il timeout della richiesta del client prima della valutazione di tutti i filtri.</span><span class="sxs-lookup"><span data-stu-id="b4c35-114">Since a message may be evaluated against multiple filters before a match is found, it is important to ensure that the client request does not time out before all filters can be evaluated.</span></span> <span data-ttu-id="b4c35-115">Un filtro personalizzato deve pertanto contenere solo il codice necessario per valutare il contenuto o gli attributi di un messaggio in modo da determinare se corrisponde o meno ai criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="b4c35-115">Therefore a custom filter should contain only the code necessary to evaluate the contents or attributes of a message in order to determine if it matches the filter criteria.</span></span>  
  
 <span data-ttu-id="b4c35-116">In generale, quando si implementa un filtro personalizzato è necessario evitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b4c35-116">In general, you should avoid the following when implementing a custom filter:</span></span>  
  
- <span data-ttu-id="b4c35-117">I/O, ad esempio salvataggio dei dati su disco o in un database.</span><span class="sxs-lookup"><span data-stu-id="b4c35-117">IO, such as saving data to disk or to a database.</span></span>  
  
- <span data-ttu-id="b4c35-118">Elaborazione non necessaria, ad esempio cicli su più record in un documento.</span><span class="sxs-lookup"><span data-stu-id="b4c35-118">Unnecessary processing, such as looping over multiple records in a document.</span></span>  
  
- <span data-ttu-id="b4c35-119">Operazioni di blocco, ad esempio chiamate che comportano l'acquisizione di un blocco su risorse condivise o l'esecuzione di ricerche in un database.</span><span class="sxs-lookup"><span data-stu-id="b4c35-119">Blocking operations, such as calls that involve obtaining a lock on shared resources or performing lookups against a database.</span></span>  
  
 <span data-ttu-id="b4c35-120">Prima di utilizzare un filtro personalizzato in un ambiente di produzione, è necessario eseguire test delle prestazioni per determinare la durata di tempo media richiesta dal filtro per la valutazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="b4c35-120">Before using a custom filter in a production environment, you should run performance tests to determine the average length of time that the filter takes to evaluate a message.</span></span> <span data-ttu-id="b4c35-121">In combinazione con il tempo di elaborazione medio degli altri filtri utilizzati nella tabella dei filtri, sarà in tal modo possibile determinare in maniera accurata il valore di timeout massimo che deve essere specificato dall'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b4c35-121">When combined with the average processing time of the other filters used in the filter table, this will allow you to accurately determine the maximum timeout value that should be specified by the client application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="b4c35-122">Uso</span><span class="sxs-lookup"><span data-stu-id="b4c35-122">Usage</span></span>  
 <span data-ttu-id="b4c35-123">Per utilizzare il filtro personalizzato con il servizio di routing, è necessario aggiungerlo alla tabella dei filtri specificando una nuova voce di filtro di tipo "Personalizzato", il nome completo del tipo di messaggio e il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b4c35-123">In order to use your custom filter with the Routing Service, you must add it to the filter table by specifying a new filter entry of type "Custom," the fully qualified type name of the message filter, and the name of your assembly.</span></span>  <span data-ttu-id="b4c35-124">Come nel caso di altri elementi MessageFilters, è possibile specificare la stringa filterData che verrà passata al costruttore del filtro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b4c35-124">As with other MessageFilters, you can specify the string filterData that will be passed to your custom filter’s constructor.</span></span>  
  
 <span data-ttu-id="b4c35-125">Negli esempi seguenti viene illustrato l'utilizzo di un filtro personalizzato con il servizio di routing:</span><span class="sxs-lookup"><span data-stu-id="b4c35-125">The following examples demonstrate using a custom filter with the Routing Service:</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"
            customType="CustomAssembly.MyMessageFilter,
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```
