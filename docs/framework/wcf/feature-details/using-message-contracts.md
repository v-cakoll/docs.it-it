---
title: Utilizzo dei contratti di messaggio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
ms.openlocfilehash: 1b102b97c62df0bb8b031ded0f9165a11f8a8911
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600270"
---
# <a name="using-message-contracts"></a><span data-ttu-id="5a580-102">Utilizzo dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-102">Using Message Contracts</span></span>
<span data-ttu-id="5a580-103">In genere, quando si compilano applicazioni Windows Communication Foundation (WCF), gli sviluppatori prestano particolare attenzione alle strutture dei dati e ai problemi di serializzazione e non devono preoccuparsi della struttura dei messaggi in cui sono trasportati i dati.</span><span class="sxs-lookup"><span data-stu-id="5a580-103">Typically when building Windows Communication Foundation (WCF) applications, developers pay close attention to the data structures and serialization issues and do not need to concern themselves with the structure of the messages in which the data is carried.</span></span> <span data-ttu-id="5a580-104">Per queste applicazioni, la creazione dei contratti dati per i parametri o dei valori restituiti è semplice.</span><span class="sxs-lookup"><span data-stu-id="5a580-104">For these applications, creating data contracts for the parameters or return values is straightforward.</span></span> <span data-ttu-id="5a580-105">Per ulteriori informazioni, vedere [specifica trasferimento dati nei contratti di servizio](specifying-data-transfer-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="5a580-105">(For more information, see [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md).)</span></span>  
  
 <span data-ttu-id="5a580-106">Talvolta, tuttavia, il controllo completo della struttura di un messaggio SOAP è importante quanto quello del suo contenuto.</span><span class="sxs-lookup"><span data-stu-id="5a580-106">However, sometimes complete control over the structure of a SOAP message is just as important as control over its contents.</span></span> <span data-ttu-id="5a580-107">Questo è particolarmente vero quando l'interoperabilità è importante o per controllare in modo specifico problemi di sicurezza a livello di messaggio o di parte di esso.</span><span class="sxs-lookup"><span data-stu-id="5a580-107">This is especially true when interoperability is important or to specifically control security issues at the level of the message or message part.</span></span> <span data-ttu-id="5a580-108">In questi casi, è possibile creare un *contratto di messaggio* che consente di specificare la struttura del messaggio SOAP preciso necessario.</span><span class="sxs-lookup"><span data-stu-id="5a580-108">In these cases, you can create a *message contract* that enables you to specify the structure of the precise SOAP message required.</span></span>  
  
 <span data-ttu-id="5a580-109">In questo argomento viene illustrato come utilizzare i vari attributi del contratto di messaggio per creare un contratto di messaggio specifico per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-109">This topic discusses how to use the various message contract attributes to create a specific message contract for your operation.</span></span>  
  
## <a name="using-message-contracts-in-operations"></a><span data-ttu-id="5a580-110">Utilizzo dei contratti di messaggio nelle operazioni</span><span class="sxs-lookup"><span data-stu-id="5a580-110">Using Message Contracts in Operations</span></span>  
 <span data-ttu-id="5a580-111">WCF supporta le operazioni modellate nello *stile RPC (Remote Procedure Call)* o nello *stile di messaggistica*.</span><span class="sxs-lookup"><span data-stu-id="5a580-111">WCF supports operations modeled on either the *remote procedure call (RPC) style* or the *messaging style*.</span></span> <span data-ttu-id="5a580-112">In un'operazione in stile RPC, è possibile utilizzare qualsiasi tipo serializzabile e si ha accesso alle funzionalità disponibili alle chiamate locali, ad esempio più parametri e i parametri `ref` e `out`.</span><span class="sxs-lookup"><span data-stu-id="5a580-112">In an RPC-style operation, you can use any serializable type, and you have access to the features that are available to local calls, such as multiple parameters and `ref` and `out` parameters.</span></span> <span data-ttu-id="5a580-113">In questo stile, la forma di serializzazione scelta controlla la struttura dei dati nei messaggi sottostanti e il runtime WCF crea i messaggi per supportare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-113">In this style, the form of serialization chosen controls the structure of the data in the underlying messages, and the WCF runtime creates the messages to support the operation.</span></span> <span data-ttu-id="5a580-114">Ciò consente agli sviluppatori che non hanno dimestichezza con SOAP e messaggi SOAP di creare rapidamente e facilmente applicazioni di servizio e di utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="5a580-114">This enables developers who are not familiar with SOAP and SOAP messages to quickly and easily create and use service applications.</span></span>  
  
 <span data-ttu-id="5a580-115">Nell'esempio di codice seguente viene illustrata un'operazione di servizio modellata sullo stile RPC.</span><span class="sxs-lookup"><span data-stu-id="5a580-115">The following code example shows a service operation modeled on the RPC style.</span></span>  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 <span data-ttu-id="5a580-116">Un contratto dati è in genere sufficiente per definire lo schema per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="5a580-116">Normally, a data contract is sufficient to define the schema for the messages.</span></span> <span data-ttu-id="5a580-117">Nell'esempio precedente, è sufficiente per la maggior parte delle applicazioni se `BankingTransaction` e `BankingTransactionResponse` hanno contratti dati per definire il contenuto dei messaggi SOAP sottostanti.</span><span class="sxs-lookup"><span data-stu-id="5a580-117">For instance, in the preceding example, it is sufficient for most applications if `BankingTransaction` and `BankingTransactionResponse` have data contracts to define the contents of the underlying SOAP messages.</span></span> <span data-ttu-id="5a580-118">Per ulteriori informazioni sui contratti dati, vedere [utilizzo di contratti dati](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="5a580-118">For more information about data contracts, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="5a580-119">Talvolta è tuttavia necessario controllare esattamente la modalità di trasmissione in rete della struttura del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="5a580-119">However, occasionally it is necessary to precisely control how the structure of the SOAP message transmitted over the wire.</span></span> <span data-ttu-id="5a580-120">Lo scenario più comune è l'inserimento di intestazioni SOAP personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5a580-120">The most common scenario for this is inserting custom SOAP headers.</span></span> <span data-ttu-id="5a580-121">Un altro scenario comune è quello della definizione di proprietà di sicurezza per le intestazioni e il corpo del messaggio, ovvero, quando è necessario decidere se questi elementi devono essere firmati digitalmente e crittografati.</span><span class="sxs-lookup"><span data-stu-id="5a580-121">Another common scenario is to define security properties for the message's headers and body, that is, to decide whether these elements are digitally signed and encrypted.</span></span> <span data-ttu-id="5a580-122">Infine, alcuni stack SOAP di terze parti richiedono che i messaggi abbiano un formato specifico.</span><span class="sxs-lookup"><span data-stu-id="5a580-122">Finally, some third-party SOAP stacks require messages be in a specific format.</span></span> <span data-ttu-id="5a580-123">Questo controllo è fornito da operazioni in stile messaggistica.</span><span class="sxs-lookup"><span data-stu-id="5a580-123">Messaging-style operations provide this control.</span></span>  
  
 <span data-ttu-id="5a580-124">Un'operazione in stile messaggistica ha al massimo un parametro e un valore restituito in cui entrambi i tipi sono tipi di messaggio, ovvero, vengono serializzati direttamente in una struttura del messaggio SOAP specificata.</span><span class="sxs-lookup"><span data-stu-id="5a580-124">A messaging-style operation has at most one parameter and one return value where both types are message types; that is, they serialize directly into a specified SOAP message structure.</span></span> <span data-ttu-id="5a580-125">Può trattarsi di un qualsiasi tipo contrassegnato con <xref:System.ServiceModel.MessageContractAttribute> o del tipo <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="5a580-125">This may be any type marked with the <xref:System.ServiceModel.MessageContractAttribute> or the <xref:System.ServiceModel.Channels.Message> type.</span></span> <span data-ttu-id="5a580-126">Nell'esempio di codice seguente viene illustrata un'operazione simile allo stile RCP precedente, ma in cui viene utilizzato lo stile di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="5a580-126">The following code example shows an operation similar to the preceding RCP-style, but which uses the messaging style.</span></span>  
  
 <span data-ttu-id="5a580-127">Se, ad esempio, `BankingTransaction` e `BankingTransactionResponse` sono entrambi tipi di contratti di messaggio, il codice nelle operazioni seguenti è valido.</span><span class="sxs-lookup"><span data-stu-id="5a580-127">For example, if `BankingTransaction` and `BankingTransactionResponse` are both types that are message contracts, then the code in the following operations is valid.</span></span>  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 <span data-ttu-id="5a580-128">Il codice seguente, tuttavia, non è valido.</span><span class="sxs-lookup"><span data-stu-id="5a580-128">However, the following code is invalid.</span></span>  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 <span data-ttu-id="5a580-129">Per qualsiasi operazione che implica un tipo di contratto di messaggio e che non segue uno schema valido, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a580-129">An exception is thrown for any operation that involves a message contract type and that does not follow one of the valid patterns.</span></span> <span data-ttu-id="5a580-130">Le operazioni che non implicano tipi di contratto di messaggio non sono ovviamente soggette a queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="5a580-130">Of course, operations that do not involve message contract types are not subject to these restrictions.</span></span>  
  
 <span data-ttu-id="5a580-131">Se un tipo ha sia un contratto di messaggio che un contratto dati, quando viene utilizzato in un'operazione viene considerato solo il suo contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-131">If a type has both a message contract and a data contract, only its message contract is considered when the type is used in an operation.</span></span>  
  
## <a name="defining-message-contracts"></a><span data-ttu-id="5a580-132">Definizione dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-132">Defining Message Contracts</span></span>  
 <span data-ttu-id="5a580-133">Per definire un contratto di messaggio per un tipo, ovvero, per definire il mapping tra il tipo e una SOAP envelope, applicare <xref:System.ServiceModel.MessageContractAttribute> al tipo.</span><span class="sxs-lookup"><span data-stu-id="5a580-133">To define a message contract for a type (that is, to define the mapping between the type and a SOAP envelope), apply the <xref:System.ServiceModel.MessageContractAttribute> to the type.</span></span> <span data-ttu-id="5a580-134">Applicare quindi <xref:System.ServiceModel.MessageHeaderAttribute> ai membri del tipo che si desidera trasformare in intestazioni SOAP e applicare <xref:System.ServiceModel.MessageBodyMemberAttribute> ai membri che si desidera trasformare in parti del corpo SOAP del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-134">Then apply the <xref:System.ServiceModel.MessageHeaderAttribute> to those members of the type you want to make into SOAP headers, and apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to those members you want to make into parts of the SOAP body of the message.</span></span>  
  
 <span data-ttu-id="5a580-135">Nel codice seguente viene fornito un esempio dell'utilizzo di un contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-135">The following code provides an example of using a message contract.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader] public DateTime transactionDate;  
  [MessageBodyMember] private Account sourceAccount;  
  [MessageBodyMember] private Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 <span data-ttu-id="5a580-136">Quando si utilizza questo tipo come parametro delle operazioni, viene generata la seguente SOAP envelope:</span><span class="sxs-lookup"><span data-stu-id="5a580-136">When using this type as an operation parameter, the following SOAP envelope is generated:</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
    <h:transactionDate xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">2012-02-16T16:10:00</h:transactionDate>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <BankingTransaction xmlns="http://tempuri.org/">  
      <amount>0</amount>  
      <sourceAccount xsi:nil="true"/>  
      <targetAccount xsi:nil="true"/>  
    </BankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="5a580-137">Si noti che `operation` e `transactionDate` vengono visualizzati come intestazioni SOAP e il corpo SOAP è costituito da un elemento wrapper `BankingTransaction` che contiene `sourceAccount`, `targetAccount` e `amount`.</span><span class="sxs-lookup"><span data-stu-id="5a580-137">Notice that `operation` and `transactionDate` appear as SOAP headers and the SOAP body consists of a wrapper element `BankingTransaction` containing `sourceAccount`,`targetAccount`, and `amount`.</span></span>  
  
 <span data-ttu-id="5a580-138">È possibile applicare <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute> a tutti i campi, le proprietà e gli eventi, indipendentemente dal fatto che siano pubblici, privati, protetti o interni.</span><span class="sxs-lookup"><span data-stu-id="5a580-138">You can apply the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> to all fields, properties, and events, regardless of whether they are public, private, protected, or internal.</span></span>  
  
 <span data-ttu-id="5a580-139"><xref:System.ServiceModel.MessageContractAttribute> consente di specificare gli attributi WrapperName e WrapperNamespace che determinano il nome dell'elemento wrapper nel corpo del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="5a580-139">The <xref:System.ServiceModel.MessageContractAttribute> allows you to specify the WrapperName and WrapperNamespace attributes which control the name of the wrapper element in the body of the SOAP message.</span></span> <span data-ttu-id="5a580-140">Per impostazione predefinita, il nome del tipo di contratto di messaggio viene utilizzato per il wrapper e lo spazio dei nomi in cui il contratto di messaggio viene definito. `http://tempuri.org/` viene utilizzato come spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="5a580-140">By default the name of the message contract type is used for the wrapper and the namespace in which the message contract is defined `http://tempuri.org/` is used as the default namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a580-141">Gli attributi <xref:System.Runtime.Serialization.KnownTypeAttribute> vengono ignorati nei contratti di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-141"><xref:System.Runtime.Serialization.KnownTypeAttribute> attributes are ignored in message contracts.</span></span> <span data-ttu-id="5a580-142">Se è richiesto un <xref:System.Runtime.Serialization.KnownTypeAttribute>, inserirlo nell'operazione in cui è utilizzato il contratto di messaggio interessato.</span><span class="sxs-lookup"><span data-stu-id="5a580-142">If a <xref:System.Runtime.Serialization.KnownTypeAttribute> is required, place it on the operation that is using the message contract in question.</span></span>  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a><span data-ttu-id="5a580-143">Controllo di intestazione, nomi di parti del corpo e spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="5a580-143">Controlling Header and Body Part Names and Namespaces</span></span>  
 <span data-ttu-id="5a580-144">Nella rappresentazione SOAP di un contratto di messaggio, ogni intestazione e parte del corpo esegue il mapping a un elemento XML che ha un nome e uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5a580-144">In the SOAP representation of a message contract, each header and body part maps to an XML element that has a name and a namespace.</span></span>  
  
 <span data-ttu-id="5a580-145">Per impostazione predefinita, lo spazio dei nomi corrisponde allo spazio dei nomi del contratto di servizio al quale partecipa il messaggio e il nome è determinato dal nome del membro al quale vengono applicati gli attributi <xref:System.ServiceModel.MessageHeaderAttribute> o <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a580-145">By default, the namespace is the same as the namespace of the service contract that the message is participating in, and the name is determined by the member name to which the <xref:System.ServiceModel.MessageHeaderAttribute> or the <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes are applied.</span></span>  
  
 <span data-ttu-id="5a580-146">È possibile cambiare queste impostazioni predefinite modificando <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> e <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (nella classe padre degli attributi <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute>).</span><span class="sxs-lookup"><span data-stu-id="5a580-146">You can change these defaults by manipulating the <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (on the parent class of the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes).</span></span>  
  
 <span data-ttu-id="5a580-147">Si consideri la classe nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-147">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="5a580-148">In questo esempio, l'intestazione `IsAudited` è nello spazio dei nomi specificato nel codice e la parte del corpo che rappresenta il membro `theData` è rappresentata da un elemento XML con il nome `transactionData`.</span><span class="sxs-lookup"><span data-stu-id="5a580-148">In this example, the `IsAudited` header is in the namespace specified in the code, and the body part that represents the `theData` member is represented by an XML element with the name `transactionData`.</span></span> <span data-ttu-id="5a580-149">Di seguito è riportato il codice XML generato per questo contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-149">The following shows the XML generated for this message contract.</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:IsAudited xmlns:h="http://schemas.contoso.com/auditing/2005" xmlns="http://schemas.contoso.com/auditing/2005">false</h:IsAudited>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <AuditedBankingTransaction xmlns="http://tempuri.org/">  
      <transactionData/>  
    </AuditedBankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a><span data-ttu-id="5a580-150">Controllo dell'incapsulamento di parti di corpo SOAP</span><span class="sxs-lookup"><span data-stu-id="5a580-150">Controlling Whether the SOAP Body Parts Are Wrapped</span></span>  
 <span data-ttu-id="5a580-151">Per impostazione predefinita, le parti di corpo SOAP vengono serializzate in un elemento incapsulato.</span><span class="sxs-lookup"><span data-stu-id="5a580-151">By default, the SOAP body parts are serialized inside a wrapped element.</span></span> <span data-ttu-id="5a580-152">Nel codice seguente, ad esempio, viene illustrato l'elemento wrapper `HelloGreetingMessage` generato dal nome del tipo <xref:System.ServiceModel.MessageContractAttribute> nel contratto di messaggio per il messaggio `HelloGreetingMessage`.</span><span class="sxs-lookup"><span data-stu-id="5a580-152">For example, the following code shows the `HelloGreetingMessage` wrapper element generated from the name of the <xref:System.ServiceModel.MessageContractAttribute> type in the message contract for the `HelloGreetingMessage` message.</span></span>  
  
[!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
[!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 <span data-ttu-id="5a580-153">Per sopprimere l'elemento wrapper, impostare la proprietà <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="5a580-153">To suppress the wrapper element, set the <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> property to `false`.</span></span> <span data-ttu-id="5a580-154">Per controllare il nome e lo spazio dei nomi dell'elemento wrapper, utilizzare le proprietà <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> e <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a580-154">To control the name and the namespace of the wrapper element, use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> and <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a580-155">La presenza di più di una parte del corpo del messaggio in messaggi non incapsulati non è conforme a WS-I Basic Profile 1.1 e non è consigliata quando si progettano nuovi contratti di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-155">Having more than one message body part in messages that are not wrapped is not compliant with WS-I Basic Profile 1.1 and is not recommended when designing new message contracts.</span></span> <span data-ttu-id="5a580-156">In certi scenari di interoperabilità, può tuttavia essere necessario avere più di una parte del corpo del messaggio non incapsulato.</span><span class="sxs-lookup"><span data-stu-id="5a580-156">However, it may be necessary to have more than one unwrapped message body part in certain specific interoperability scenarios.</span></span> <span data-ttu-id="5a580-157">Se si ha intenzione di trasmettere più di un pezzo di dati in un corpo del messaggio, è consigliato utilizzare la modalità predefinita (incapsulata).</span><span class="sxs-lookup"><span data-stu-id="5a580-157">If you are going to transmit more than one piece of data in a message body, it is recommended to use the default (wrapped) mode.</span></span> <span data-ttu-id="5a580-158">La presenza di più di un'intestazione del messaggio nei messaggi non incapsulati è completamente accettabile.</span><span class="sxs-lookup"><span data-stu-id="5a580-158">Having more than one message header in unwrapped messages is completely acceptable.</span></span>  
  
## <a name="using-custom-types-inside-message-contracts"></a><span data-ttu-id="5a580-159">Utilizzo di tipi personalizzati nei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-159">Using Custom Types Inside Message Contracts</span></span>  
 <span data-ttu-id="5a580-160">Ogni singola intestazione del messaggio e parte del corpo del messaggio viene serializzata (trasformata in XML) utilizzando il motore di serializzazione scelto per il contratto di servizio in cui il messaggio è utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5a580-160">Each individual message header and message body part is serialized (turned into XML) using the chosen serialization engine for the service contract where the message is used.</span></span> <span data-ttu-id="5a580-161">Il motore di serializzazione predefinito, `XmlFormatter`, è in grado di gestire qualsiasi tipo che abbia un contratto dati, in modo esplicito (con <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) o implicito (se si tratta di un tipo primitivo, con <xref:System.SerializableAttribute?displayProperty=nameWithType> e così via).</span><span class="sxs-lookup"><span data-stu-id="5a580-161">The default serialization engine, the `XmlFormatter`, can handle any type that has a data contract, either explicitly (by having the <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) or implicitly (by being a primitive type, having the <xref:System.SerializableAttribute?displayProperty=nameWithType>, and so on).</span></span> <span data-ttu-id="5a580-162">Per ulteriori informazioni, vedere [utilizzo di contratti dati](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="5a580-162">For more information, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="5a580-163">Nell'esempio precedente, i tipi `Operation` e `BankingTransactionData` devono avere un contratto dati e `transactionDate` è serializzabile perché <xref:System.DateTime> è un primitivo e, di conseguenza, ha un contratto dati implicito.</span><span class="sxs-lookup"><span data-stu-id="5a580-163">In the preceding example, the `Operation` and `BankingTransactionData` types must have a data contract, and `transactionDate` is serializable because <xref:System.DateTime> is a primitive (and so has an implicit data contract).</span></span>  
  
 <span data-ttu-id="5a580-164">È tuttavia possibile passare a un diverso motore di serializzazione, `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="5a580-164">However, it is possible to switch to a different serialization engine, the `XmlSerializer`.</span></span> <span data-ttu-id="5a580-165">Se si sceglie di cambiare motore, è necessario assicurarsi che tutti i tipi utilizzati per le intestazioni dei messaggi e le parti del corpo siano serializzabili utilizzando `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="5a580-165">If you make such a switch, you should ensure that all of the types used for message headers and body parts are serializable using the `XmlSerializer`.</span></span>  
  
## <a name="using-arrays-inside-message-contracts"></a><span data-ttu-id="5a580-166">Utilizzo di matrici nei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-166">Using Arrays Inside Message Contracts</span></span>  
 <span data-ttu-id="5a580-167">È possibile utilizzare matrici di elementi ripetuti nei contratti di messaggio in due modi.</span><span class="sxs-lookup"><span data-stu-id="5a580-167">You can use arrays of repeating elements in message contracts in two ways.</span></span>  
  
 <span data-ttu-id="5a580-168">Il primo consiste nell'utilizzare un <xref:System.ServiceModel.MessageHeaderAttribute> o un <xref:System.ServiceModel.MessageBodyMemberAttribute> direttamente nella matrice.</span><span class="sxs-lookup"><span data-stu-id="5a580-168">The first is to use a <xref:System.ServiceModel.MessageHeaderAttribute> or a <xref:System.ServiceModel.MessageBodyMemberAttribute> directly on the array.</span></span> <span data-ttu-id="5a580-169">In questo caso, l'intera matrice viene serializzata come un solo elemento, ovvero, come un'unica intestazione o un'unica parte del corpo, con in più elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="5a580-169">In this case, the entire array is serialized as one element (that is, one header or one body part) with multiple child elements.</span></span> <span data-ttu-id="5a580-170">Si consideri la classe nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-170">Consider the class in the following example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 <span data-ttu-id="5a580-171">Il risultato nelle intestazioni SOAP è simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-171">This results in SOAP headers is similar to the following.</span></span>  
  
```xml  
<BankingDepositLog>  
<numRecords>3</numRecords>  
<records>  
  <DepositRecord>Record1</DepositRecord>  
  <DepositRecord>Record2</DepositRecord>  
  <DepositRecord>Record3</DepositRecord>  
</records>  
<branchID>20643</branchID>  
</BankingDepositLog>  
```  
  
 <span data-ttu-id="5a580-172">In alternativa, è possibile utilizzare <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a580-172">An alternative to this is to use the <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span></span> <span data-ttu-id="5a580-173">In questo caso, ogni elemento della matrice viene serializzato in modo indipendente affinché abbia un'intestazione, in modo simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-173">In this case, each array element is serialized independently and so that each array element has one header, similar to the following.</span></span>  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 <span data-ttu-id="5a580-174">Il nome predefinito per le voci della matrice è il nome del membro al quale vengono applicati gli attributi <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a580-174">The default name for array entries is the name of the member to which the <xref:System.ServiceModel.MessageHeaderArrayAttribute> attributes is applied.</span></span>  
  
 <span data-ttu-id="5a580-175">L'attributo <xref:System.ServiceModel.MessageHeaderArrayAttribute> eredita da <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a580-175">The <xref:System.ServiceModel.MessageHeaderArrayAttribute> attribute inherits from the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="5a580-176">Ha lo stesso set di funzionalità degli attributi non di matrice, ad esempio, è possibile impostare l'ordine, il nome e lo spazio dei nomi per una matrice di intestazioni nella stessa modalità utilizzata per una singola intestazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-176">It has the same set of features as the non-array attributes, for example, it is possible to set the order, name, and namespace for an array of headers in the same way you set it for a single header.</span></span> <span data-ttu-id="5a580-177">Quando si utilizza la proprietà `Order` su una matrice, tale proprietà viene applicata alla matrice intera.</span><span class="sxs-lookup"><span data-stu-id="5a580-177">When you use the `Order` property on an array, it applies to the entire array.</span></span>  
  
 <span data-ttu-id="5a580-178">È possibile applicare <xref:System.ServiceModel.MessageHeaderArrayAttribute> solo alle matrici, non alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="5a580-178">You can apply the <xref:System.ServiceModel.MessageHeaderArrayAttribute> only to arrays, not collections.</span></span>  
  
## <a name="using-byte-arrays-in-message-contracts"></a><span data-ttu-id="5a580-179">Utilizzo di matrici di byte nei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-179">Using Byte Arrays in Message Contracts</span></span>  
 <span data-ttu-id="5a580-180">Le matrici di byte, quando sono utilizzate con attributi non di matrice (<xref:System.ServiceModel.MessageBodyMemberAttribute> e <xref:System.ServiceModel.MessageHeaderAttribute>), non vengono trattate come matrici ma come un tipo primitivo speciale rappresentato come dati con codifica Base64 nell'XML risultante.</span><span class="sxs-lookup"><span data-stu-id="5a580-180">Byte arrays, when used with the non-array attributes (<xref:System.ServiceModel.MessageBodyMemberAttribute> and <xref:System.ServiceModel.MessageHeaderAttribute>), are not treated as arrays but as a special primitive type represented as Base64-encoded data in the resulting XML.</span></span>  
  
 <span data-ttu-id="5a580-181">Quando si utilizzano matrici di byte con l'attributo della matrice <xref:System.ServiceModel.MessageHeaderArrayAttribute>, i risultati dipendono dal serializzatore utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5a580-181">When you use byte arrays with the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the results depend on the serializer in use.</span></span> <span data-ttu-id="5a580-182">Con il serializzatore predefinito, la matrice è rappresentata sotto forma di singola voce per ogni byte.</span><span class="sxs-lookup"><span data-stu-id="5a580-182">With the default serializer, the array is represented as an individual entry for each byte.</span></span> <span data-ttu-id="5a580-183">Quando, tuttavia, è selezionato `XmlSerializer`, (utilizzando <xref:System.ServiceModel.XmlSerializerFormatAttribute> nel contratto di servizio), le matrici di byte vengono trattate come dati Base64 indipendentemente dal fatto che siano utilizzati attributi di matrice o non di matrice.</span><span class="sxs-lookup"><span data-stu-id="5a580-183">However, when the `XmlSerializer` is selected, (using the <xref:System.ServiceModel.XmlSerializerFormatAttribute> on the service contract), byte arrays are treated as Base64 data regardless of whether the array or non-array attributes are used.</span></span>  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a><span data-ttu-id="5a580-184">Firma e crittografia di parti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-184">Signing and Encrypting Parts of the Message</span></span>  
 <span data-ttu-id="5a580-185">Un contratto di messaggio può indicare se le intestazioni e/o il corpo del messaggio devono essere crittografati e firmati digitalmente.</span><span class="sxs-lookup"><span data-stu-id="5a580-185">A message contract can indicate whether the headers and/or body of the message should be digitally signed and encrypted.</span></span>  
  
 <span data-ttu-id="5a580-186">A tal fine, impostare la proprietà <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> sugli attributi <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a580-186">This is done by setting the <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> property on the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="5a580-187">La proprietà è un'enumerazione del tipo <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> e può essere impostata su <xref:System.Net.Security.ProtectionLevel.None> (nessuna crittografia o firma), <xref:System.Net.Security.ProtectionLevel.Sign> (solo firma digitale) o <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (sia crittografia che firma digitale).</span><span class="sxs-lookup"><span data-stu-id="5a580-187">The property is an enumeration of the <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> type and can be set to <xref:System.Net.Security.ProtectionLevel.None> (no encryption or signature), <xref:System.Net.Security.ProtectionLevel.Sign> (digital signature only), or <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (both encryption and a digital signature).</span></span> <span data-ttu-id="5a580-188">Il valore predefinito è <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="5a580-188">The default is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
 <span data-ttu-id="5a580-189">Affinché queste funzionalità di sicurezza funzionino, è necessario configurare correttamente l'associazione e i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="5a580-189">For these security features to work, you must properly configure the binding and behaviors.</span></span> <span data-ttu-id="5a580-190">Se vengono utilizzate senza la configurazione corretta, ad esempio se si tenta di firmare un messaggio senza fornire le proprie credenziali, al momento della convalida viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a580-190">If you use these security features without the proper configuration (for example, attempting to sign a message without supplying your credentials), an exception is thrown at validation time.</span></span>  
  
 <span data-ttu-id="5a580-191">Nel caso delle intestazioni di messaggio, il livello di protezione viene determinato singolarmente per ogni intestazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-191">For message headers, the protection level is determined individually for each header.</span></span>  
  
 <span data-ttu-id="5a580-192">Per le parti del corpo del messaggio, il livello di protezione può essere considerato come "livello minimo di protezione".</span><span class="sxs-lookup"><span data-stu-id="5a580-192">For message body parts, the protection level can be thought of as the "minimum protection level."</span></span> <span data-ttu-id="5a580-193">Il corpo ha un solo livello di protezione, indipendentemente dal numero delle sue parti.</span><span class="sxs-lookup"><span data-stu-id="5a580-193">The body has only one protection level, regardless of the number of body parts.</span></span> <span data-ttu-id="5a580-194">Il livello di protezione del corpo è determinato dall'impostazione più alta della proprietà <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> di tutte le parti del corpo.</span><span class="sxs-lookup"><span data-stu-id="5a580-194">The protection level of the body is determined by the highest <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> property setting of all the body parts.</span></span> <span data-ttu-id="5a580-195">È tuttavia necessario impostare il livello di protezione di ogni parte del corpo sul livello di protezione minimo effettivo richiesto.</span><span class="sxs-lookup"><span data-stu-id="5a580-195">However, you should set the protection level of each body part to the actual minimum protection level required.</span></span>  
  
 <span data-ttu-id="5a580-196">Si consideri la classe nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-196">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class PatientRecord  
{  
   [MessageHeader(ProtectionLevel=None)] public int recordID;  
   [MessageHeader(ProtectionLevel=Sign)] public string patientName;  
   [MessageHeader(ProtectionLevel=EncryptAndSign)] public string SSN;  
   [MessageBodyMember(ProtectionLevel=None)] public string comments;  
   [MessageBodyMember(ProtectionLevel=Sign)] public string diagnosis;  
   [MessageBodyMember(ProtectionLevel=EncryptAndSign)] public string medicalHistory;  
}  
```  
  
 <span data-ttu-id="5a580-197">In questo esempio, l'intestazione `recordID` non è protetta, la parte `patientName` è `signed` e la parte `SSN` è crittografata e firmata.</span><span class="sxs-lookup"><span data-stu-id="5a580-197">In this example, the `recordID` header is not protected, `patientName` is `signed`, and `SSN` is encrypted and signed.</span></span> <span data-ttu-id="5a580-198">Ad almeno una parte del corpo, `medicalHistory`, è applicato <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, pertanto tutto il corpo del messaggio è crittografato e firmato anche se i commenti e le parti del corpo di diagnosi specificano livelli di protezione inferiori.</span><span class="sxs-lookup"><span data-stu-id="5a580-198">At least one body part, `medicalHistory`, has <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> applied, and thus the entire message body is encrypted and signed, even though the comments and diagnosis body parts specify lower protection levels.</span></span>  
  
## <a name="soap-action"></a><span data-ttu-id="5a580-199">Azione SOAP</span><span class="sxs-lookup"><span data-stu-id="5a580-199">SOAP Action</span></span>  
 <span data-ttu-id="5a580-200">SOAP e gli standard dei servizi Web correlati definiscono una proprietà chiamata `Action` che può essere presente per ogni messaggio SOAP inviato.</span><span class="sxs-lookup"><span data-stu-id="5a580-200">SOAP and related Web services standards define a property called `Action` that can be present for every SOAP message sent.</span></span> <span data-ttu-id="5a580-201">Il valore di questa proprietà è controllato dalle proprietà <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> e <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-201">The operation's <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> properties control the value of this property.</span></span>  
  
## <a name="soap-header-attributes"></a><span data-ttu-id="5a580-202">Attributi di intestazione SOAP</span><span class="sxs-lookup"><span data-stu-id="5a580-202">SOAP Header Attributes</span></span>  
 <span data-ttu-id="5a580-203">Lo standard SOAP definisce gli attributi che possono esistere in un'intestazione. Tali attributi sono:</span><span class="sxs-lookup"><span data-stu-id="5a580-203">The SOAP standard defines the following attributes that may exist on a header:</span></span>  
  
- <span data-ttu-id="5a580-204">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span><span class="sxs-lookup"><span data-stu-id="5a580-204">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span></span>  
  
- `MustUnderstand`  
  
- `Relay`  
  
 <span data-ttu-id="5a580-205">L'attributo `Actor` o `Role` specifica l'URI (Uniform Resource Identifier) del nodo al quale è destinata una determinata intestazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-205">The `Actor` or `Role` attribute specifies the Uniform Resource Identifier (URI) of the node for which a given header is intended.</span></span> <span data-ttu-id="5a580-206">L'attributo `MustUnderstand` specifica se il nodo che elabora l'intestazione deve comprenderla.</span><span class="sxs-lookup"><span data-stu-id="5a580-206">The `MustUnderstand` attribute specifies whether the node processing the header must understand it.</span></span> <span data-ttu-id="5a580-207">L'attributo `Relay` specifica se l'intestazione deve essere inoltrata ai nodi downstream.</span><span class="sxs-lookup"><span data-stu-id="5a580-207">The `Relay` attribute specifies whether the header is to be relayed to downstream nodes.</span></span> <span data-ttu-id="5a580-208">WCF non esegue alcuna elaborazione di questi attributi sui messaggi in ingresso, ad eccezione dell' `MustUnderstand` attributo, come specificato nella sezione "controllo delle versioni dei contratti di messaggio" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5a580-208">WCF does not perform any processing of these attributes on incoming messages, except for the `MustUnderstand` attribute, as specified in the "Message Contract Versioning" section later in this topic.</span></span> <span data-ttu-id="5a580-209">Consente tuttavia di leggerli e scriverli come appropriato, come nella descrizione seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-209">However, it allows you to read and write these attributes as necessary, as in the following description.</span></span>  
  
 <span data-ttu-id="5a580-210">Quando si invia un messaggio, per impostazione predefinita questi attributi non vengono creati.</span><span class="sxs-lookup"><span data-stu-id="5a580-210">When sending a message, these attributes are not emitted by default.</span></span> <span data-ttu-id="5a580-211">È possibile modificare l'impostazione in due modi.</span><span class="sxs-lookup"><span data-stu-id="5a580-211">You can change this in two ways.</span></span> <span data-ttu-id="5a580-212">In primo luogo, è possibile impostare staticamente gli attributi su qualsiasi valore desiderato modificando le proprietà <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> e <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType>, come mostrato nell'esempio di codice che segue.</span><span class="sxs-lookup"><span data-stu-id="5a580-212">First, you may statically set the attributes to any desired values by changing the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType>, and <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> properties, as shown in the following code example.</span></span> <span data-ttu-id="5a580-213">Si noti che non esiste alcuna proprietà `Role`. Nel caso in cui si utilizzi SOAP 1.2, se si imposta la proprietà <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> viene creato l'attributo `Role`.</span><span class="sxs-lookup"><span data-stu-id="5a580-213">(Note that there is no `Role` property; setting the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> property emits the `Role` attribute if you are using SOAP 1.2).</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="5a580-214">La seconda modalità di controllo di questi attributi è dinamica, tramite codice.</span><span class="sxs-lookup"><span data-stu-id="5a580-214">The second way to control these attributes is dynamically, through code.</span></span> <span data-ttu-id="5a580-215">In questo caso, incapsulare il tipo di intestazione desiderato nel tipo <xref:System.ServiceModel.MessageHeader%601>, per essere certi di non confondere questo tipo con la versione non generica, e utilizzare il tipo insieme a <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a580-215">You can achieve this by wrapping the desired header type in the <xref:System.ServiceModel.MessageHeader%601> type (be sure not to confuse this type with the non-generic version) and by using the type together with the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="5a580-216">Quindi, è possibile utilizzare proprietà in <xref:System.ServiceModel.MessageHeader%601> per impostare gli attributi SOAP, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-216">Then, you can use properties on the <xref:System.ServiceModel.MessageHeader%601> to set the SOAP attributes, as shown in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public MessageHeader<bool> IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
// application code:  
BankingTransaction bt = new BankingTransaction();  
bt.IsAudited = new MessageHeader<bool>();  
bt.IsAudited.Content = false; // Set IsAudited header value to "false"  
bt.IsAudited.Actor="http://auditingservice.contoso.com";  
bt.IsAudited.MustUnderstand=true;  
```  
  
 <span data-ttu-id="5a580-217">Se si utilizza sia il meccanismo di controllo dinamico sia quello statico, per impostazione predefinita vengono utilizzate le impostazioni statiche che, tuttavia, in seguito possono essere sottoposte a override utilizzando il meccanismo dinamico, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-217">If you use both the dynamic and the static control mechanisms, the static settings are used as a default but can later be overridden by using the dynamic mechanism, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 <span data-ttu-id="5a580-218">È consentito creare intestazioni ripetute con il controllo dinamico degli attributi, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-218">Creating repeated headers with dynamic attribute control is allowed, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 <span data-ttu-id="5a580-219">Sul lato ricevente, la lettura di questi attributi SOAP può essere eseguita solo se si utilizza la classe <xref:System.ServiceModel.MessageHeader%601> per l'intestazione nel tipo.</span><span class="sxs-lookup"><span data-stu-id="5a580-219">On the receiving side, reading these SOAP attributes can only be done if the <xref:System.ServiceModel.MessageHeader%601> class is used for the header in the type.</span></span> <span data-ttu-id="5a580-220">Per individuare le impostazioni degli attributi del messaggio ricevuto è possibile esaminare le proprietà `Actor`, `Relay` o `MustUnderstand` di un'intestazione di tipo <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="5a580-220">Examine the `Actor`, `Relay`, or `MustUnderstand` properties of a header of the <xref:System.ServiceModel.MessageHeader%601> type to discover the attribute settings on the received message.</span></span>  
  
 <span data-ttu-id="5a580-221">Quando si riceve un messaggio e quindi lo si invia nuovamente all'origine, il roundtrip delle impostazioni degli attributi SOAP viene eseguito solo per le intestazioni di tipo <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="5a580-221">When a message is received and then sent back, the SOAP attribute settings only go round-trip for headers of the <xref:System.ServiceModel.MessageHeader%601> type.</span></span>  
  
## <a name="order-of-soap-body-parts"></a><span data-ttu-id="5a580-222">Ordine delle parti del corpo SOAP</span><span class="sxs-lookup"><span data-stu-id="5a580-222">Order of SOAP Body Parts</span></span>  
 <span data-ttu-id="5a580-223">In alcune circostanze, potrebbe essere necessario controllare l'ordine delle parti del corpo.</span><span class="sxs-lookup"><span data-stu-id="5a580-223">In some circumstances, you may need to control the order of the body parts.</span></span> <span data-ttu-id="5a580-224">Per impostazione predefinita, l'ordine degli elementi del corpo è alfabetico ma può essere controllato dalla proprietà <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a580-224">The order of the body elements is alphabetical by default, but can be controlled by the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5a580-225">Questa proprietà ha la stessa semantica della proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, a parte il comportamento negli scenari di ereditarietà. Nei contratti di messaggio, i membri del corpo di tipo base non sono ordinati prima dei membri del corpo di tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="5a580-225">This property has the same semantics as the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType> property, except for the behavior in inheritance scenarios (in message contracts, base type body members are not sorted before the derived type body members).</span></span> <span data-ttu-id="5a580-226">Per ulteriori informazioni, vedere l' [ordine dei membri dati](data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="5a580-226">For more information, see [Data Member Order](data-member-order.md).</span></span>  
  
 <span data-ttu-id="5a580-227">Nell'esempio seguente, `amount` normalmente verrebbe per primo perché è primo alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="5a580-227">In the following example, `amount` would normally come first because it is first alphabetically.</span></span> <span data-ttu-id="5a580-228">La proprietà <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> l'inserisce tuttavia nella terza posizione.</span><span class="sxs-lookup"><span data-stu-id="5a580-228">However, the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> property puts it into the third position.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember(Order=1)] public Account sourceAccount;  
  [MessageBodyMember(Order=2)] public Account targetAccount;  
  [MessageBodyMember(Order=3)] public int amount;  
}  
```  
  
## <a name="message-contract-versioning"></a><span data-ttu-id="5a580-229">Controllo delle versioni dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="5a580-229">Message Contract Versioning</span></span>  
 <span data-ttu-id="5a580-230">Talvolta potrebbe essere necessario modificare contratti di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-230">Occasionally, you may need to change message contracts.</span></span> <span data-ttu-id="5a580-231">Una nuova versione dell'applicazione, ad esempio, potrebbe aggiungere un'altra intestazione a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-231">For example, a new version of your application may add an extra header to a message.</span></span> <span data-ttu-id="5a580-232">Quindi, in caso di invio dalla versione nuova a quella vecchia, il sistema deve gestire un'intestazione in più, mentre in direzione opposta deve gestirne una in meno.</span><span class="sxs-lookup"><span data-stu-id="5a580-232">Then, when sending from the new version to the old, the system must deal with an extra header, as well as a missing header when going in the other direction.</span></span>  
  
 <span data-ttu-id="5a580-233">Per il controllo delle versioni delle intestazioni, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a580-233">The following rules apply for versioning headers:</span></span>  
  
- <span data-ttu-id="5a580-234">WCF non esegue l'oggetto sulle intestazioni mancanti. i membri corrispondenti rimangono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5a580-234">WCF does not object to the missing headers—the corresponding members are left at their default values.</span></span>  
  
- <span data-ttu-id="5a580-235">WCF ignora inoltre le intestazioni aggiuntive impreviste.</span><span class="sxs-lookup"><span data-stu-id="5a580-235">WCF also ignores unexpected extra headers.</span></span> <span data-ttu-id="5a580-236">Fa eccezione a questa regola il caso di un'intestazione aggiuntiva il cui attributo `MustUnderstand` sia impostato su `true` nel messaggio SOAP in ingresso. Non essendo possibile elaborare un'intestazione che deve essere compresa, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a580-236">The one exception to this rule is if the extra header has a `MustUnderstand` attribute set to `true` in the incoming SOAP message—in this case, an exception is thrown because a header that must be understood cannot be processed.</span></span>  
  
 <span data-ttu-id="5a580-237">Per i corpi dei messaggi si applicano regole simili di controllo delle versioni, sia le parti di corpi dei messaggi mancanti che quelle aggiuntive vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="5a580-237">Message bodies have similar versioning rules—both missing and additional message body parts are ignored.</span></span>  
  
## <a name="inheritance-considerations"></a><span data-ttu-id="5a580-238">Considerazioni sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="5a580-238">Inheritance Considerations</span></span>  
 <span data-ttu-id="5a580-239">Un tipo di contratto di messaggio può ereditare da un altro tipo, a condizione che anche il tipo di base abbia un contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-239">A message contract type can inherit from another type, as long as the base type also has a message contract.</span></span>  
  
 <span data-ttu-id="5a580-240">Quando si crea o si accede a un messaggio utilizzando un tipo di contratto di messaggio che eredita da altri tipi di contratto di messaggio, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a580-240">When creating or accessing a message using a message contract type that inherits from other message contract types, the following rules apply:</span></span>  
  
- <span data-ttu-id="5a580-241">Tutte le intestazioni del messaggio nella gerarchia di ereditarietà sono raccolte insieme per formare il set completo di intestazioni per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-241">All of the message headers in the inheritance hierarchy are collected together to form the full set of headers for the message.</span></span>  
  
- <span data-ttu-id="5a580-242">Tutte le parti del corpo del messaggio nella gerarchia di ereditarietà sono raccolte insieme per formare l'intero corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-242">All of the message body parts in the inheritance hierarchy are collected together to form the full message body.</span></span> <span data-ttu-id="5a580-243">Le parti del corpo sono ordinate in base alle normali regole di ordinamento (in base alla proprietà <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> e quindi alfabeticamente), senza considerare affatto la loro posizione nella gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="5a580-243">The body parts are ordered according to the usual ordering rules (by <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property and then alphabetical), with no relevance to their place in the inheritance hierarchy.</span></span> <span data-ttu-id="5a580-244">È assolutamente sconsigliato usare l'ereditarietà del contratto di messaggio nel caso in cui le parti del corpo del messaggio si trovino a più livelli della struttura di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="5a580-244">Using message contract inheritance where message body parts occur at multiple levels of the inheritance tree is strongly discouraged.</span></span> <span data-ttu-id="5a580-245">Se una classe di base e una classe derivata definiscono un'intestazione o una parte del corpo con lo stesso nome, per archiviare il valore di quell'intestazione o di quella parte del corpo viene utilizzato il membro della classe più di base.</span><span class="sxs-lookup"><span data-stu-id="5a580-245">If a base class and a derived class define a header or a body part with the same name, the member from the base-most class is used to store the value of that header or body part.</span></span>  
  
 <span data-ttu-id="5a580-246">Si considerino le classi nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-246">Consider the classes in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class PersonRecord  
{  
  [MessageHeader(Name="ID")] public int personID;  
  [MessageBodyMember] public string patientName;  
}  
  
[MessageContract]  
public class PatientRecord : PersonRecord  
{  
  [MessageHeader(Name="ID")] public int patientID;  
  [MessageBodyMember] public string diagnosis;  
}  
```  
  
 <span data-ttu-id="5a580-247">La classe `PatientRecord` descrive un messaggio con un'intestazione chiamata `ID`.</span><span class="sxs-lookup"><span data-stu-id="5a580-247">The `PatientRecord` class describes a message with one header called `ID`.</span></span> <span data-ttu-id="5a580-248">L'intestazione corrisponde a `personID` e non al membro `patientID`, perché viene scelto il membro più di base.</span><span class="sxs-lookup"><span data-stu-id="5a580-248">The header corresponds to the `personID` and not the `patientID` member, because the base-most member is chosen.</span></span> <span data-ttu-id="5a580-249">Pertanto, in questo caso il campo `patientID` è inutile.</span><span class="sxs-lookup"><span data-stu-id="5a580-249">Thus, the `patientID` field is useless in this case.</span></span> <span data-ttu-id="5a580-250">Il corpo del messaggio contiene l'elemento `diagnosis` seguito dall'elemento `patientName`, perché questo è l'ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="5a580-250">The body of the message contains the `diagnosis` element followed by the `patientName` element, because that is the alphabetical order.</span></span> <span data-ttu-id="5a580-251">Si noti che nell'esempio viene illustrato uno schema assolutamente sconsigliato: sia il contratto di messaggio di base che quello del messaggio derivato hanno parti di corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-251">Notice that the example shows a pattern that is strongly discouraged: both the base and the derived message contracts have message body parts.</span></span>  
  
## <a name="wsdl-considerations"></a><span data-ttu-id="5a580-252">Considerazioni su WSDL</span><span class="sxs-lookup"><span data-stu-id="5a580-252">WSDL Considerations</span></span>  
 <span data-ttu-id="5a580-253">Quando si genera un contratto Web Services Description Language (WSDL) da un servizio che utilizza contratti di messaggio, è importante ricordare che non tutte le funzionalità del contratto di messaggio vengono riflesse nel WSDL risultante.</span><span class="sxs-lookup"><span data-stu-id="5a580-253">When generating a Web Services Description Language (WSDL) contract from a service that uses message contracts, it is important to remember that not all message contract features are reflected in the resulting WSDL.</span></span> <span data-ttu-id="5a580-254">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a580-254">Consider the following points:</span></span>  
  
- <span data-ttu-id="5a580-255">WSDL non è in grado di esprimere il concetto di una matrice di intestazioni.</span><span class="sxs-lookup"><span data-stu-id="5a580-255">WSDL cannot express the concept of an array of headers.</span></span> <span data-ttu-id="5a580-256">Quando si creano messaggi con una matrice di intestazioni utilizzando <xref:System.ServiceModel.MessageHeaderArrayAttribute>, il WSDL risultante riflette solo un'intestazione anziché la matrice.</span><span class="sxs-lookup"><span data-stu-id="5a580-256">When creating messages with an array of headers using the <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the resulting WSDL reflects only one header instead of the array.</span></span>  
  
- <span data-ttu-id="5a580-257">Il documento WSDL risultante non può riflettere alcune informazioni del livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="5a580-257">The resulting WSDL document may not reflect some protection-level information.</span></span>  
  
- <span data-ttu-id="5a580-258">Il tipo di messaggio generato in WSDL ha lo stesso nome della classe del tipo del contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-258">The message type generated in the WSDL has the same name as the class name of the message contract type.</span></span>  
  
- <span data-ttu-id="5a580-259">Quando si utilizza lo stesso contratto di messaggio in più operazioni, nel documento WSDL vengono generati più tipi di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-259">When using the same message contract in multiple operations, multiple message types are generated in the WSDL document.</span></span> <span data-ttu-id="5a580-260">I nomi sono resi univoci aggiungendo i numeri "2", "3" e così via, per gli utilizzi successivi.</span><span class="sxs-lookup"><span data-stu-id="5a580-260">The names are made unique by adding the numbers "2", "3", and so on, for subsequent uses.</span></span> <span data-ttu-id="5a580-261">Al momento della reimportazione in WSDL, vengono creati più tipi di contratto di messaggio, che sono identici tranne che per il nome.</span><span class="sxs-lookup"><span data-stu-id="5a580-261">When importing back the WSDL, multiple message contract types are created and are identical except for their names.</span></span>  
  
## <a name="soap-encoding-considerations"></a><span data-ttu-id="5a580-262">Considerazioni sulla codifica SOAP</span><span class="sxs-lookup"><span data-stu-id="5a580-262">SOAP Encoding Considerations</span></span>  
 <span data-ttu-id="5a580-263">WCF consente di utilizzare lo stile di codifica SOAP legacy di XML, tuttavia non è consigliabile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="5a580-263">WCF allows you to use the legacy SOAP encoding style of XML, however, its use is not recommended.</span></span> <span data-ttu-id="5a580-264">Quando si utilizza questo stile, impostando la proprietà `Use` su `Encoded` nel <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> applicato al contratto di servizio, si applicano le considerazioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a580-264">When using this style (by setting the `Use` property to `Encoded` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> applied to the service contract), the following additional considerations apply:</span></span>  
  
- <span data-ttu-id="5a580-265">Le intestazioni del messaggio non sono supportate. Ciò significa che l'attributo <xref:System.ServiceModel.MessageHeaderAttribute> e l'attributo della matrice <xref:System.ServiceModel.MessageHeaderArrayAttribute> sono incompatibili con la codifica SOAP.</span><span class="sxs-lookup"><span data-stu-id="5a580-265">The message headers are not supported; this means that the attribute <xref:System.ServiceModel.MessageHeaderAttribute> and the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute> are incompatible with SOAP encoding.</span></span>  
  
- <span data-ttu-id="5a580-266">Se il contratto di messaggio non viene incapsulato, ovvero se la proprietà <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> è impostata su `false`, può avere solo una parte del corpo.</span><span class="sxs-lookup"><span data-stu-id="5a580-266">If the message contract is not wrapped, that is, if the property <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is set to `false`, the message contract can have only one body part.</span></span>  
  
- <span data-ttu-id="5a580-267">Il nome dell'elemento wrapper per il contratto di messaggio di richiesta deve corrispondere al nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5a580-267">The name of the wrapper element for the request message contract must match the operation name.</span></span> <span data-ttu-id="5a580-268">A tale scopo, utilizzare la proprietà `WrapperName` del contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-268">Use the `WrapperName` property of the message contract for this.</span></span>  
  
- <span data-ttu-id="5a580-269">Il nome dell'elemento wrapper per il contratto di messaggio di risposta deve essere identico a quello del nome dell'operazione con il suffisso "Response".</span><span class="sxs-lookup"><span data-stu-id="5a580-269">The name of the wrapper element for the response message contract must be the same as the name of the operation suffixed by 'Response'.</span></span> <span data-ttu-id="5a580-270">A tale scopo, utilizzare la proprietà <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> del contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a580-270">Use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> property of the message contract for this.</span></span>  
  
- <span data-ttu-id="5a580-271">La codifica SOAP mantiene i riferimenti all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5a580-271">SOAP encoding preserves object references.</span></span> <span data-ttu-id="5a580-272">Si consideri il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5a580-272">For example, consider the following code.</span></span>  
  
    ```csharp  
    [MessageContract(WrapperName="updateChangeRecord")]  
    public class ChangeRecordRequest  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    [MessageContract(WrapperName="updateChangeRecordResponse")]  
    public class ChangeRecordResponse  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    // application code:  
    ChangeRecordRequest cr = new ChangeRecordRequest();  
    Person p = new Person("John Doe");  
    cr.changedBy=p;  
    cr.changedFrom=p;  
    cr.changedTo=p;  
    ```  
  
 <span data-ttu-id="5a580-273">Dopo aver serializzato il messaggio utilizzando la codifica SOAP, `changedFrom` e `changedTo` non contengono copie di `p`, ma puntano alla copia all'interno dell'elemento `changedBy`.</span><span class="sxs-lookup"><span data-stu-id="5a580-273">After serializing the message using SOAP encoding, `changedFrom` and `changedTo` do not contain their own copies of `p`, but instead point to the copy inside the `changedBy` element.</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="5a580-274">Considerazioni sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="5a580-274">Performance Considerations</span></span>  
 <span data-ttu-id="5a580-275">Ogni intestazione del messaggio e ogni parte del corpo del messaggio viene serializzata indipendentemente dalle altre.</span><span class="sxs-lookup"><span data-stu-id="5a580-275">Every message header and message body part is serialized independently of the others.</span></span> <span data-ttu-id="5a580-276">È pertanto possibile dichiarare gli stessi spazi dei nomi per ogni intestazione e parte del corpo.</span><span class="sxs-lookup"><span data-stu-id="5a580-276">Therefore, the same namespaces can be declared again for each header and body part.</span></span> <span data-ttu-id="5a580-277">Per migliorare le prestazioni, specie in termini di dimensioni del messaggio in transito, consolidare più intestazioni e parti del corpo in un'unica intestazione o parte del corpo.</span><span class="sxs-lookup"><span data-stu-id="5a580-277">To improve performance, especially in terms of the size of the message on the wire, consolidate multiple headers and body parts into a single header or body part.</span></span> <span data-ttu-id="5a580-278">Anziché, ad esempio, il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5a580-278">For example, instead of the following code:</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public Account sourceAccount;  
  [MessageBodyMember] public Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 <span data-ttu-id="5a580-279">Utilizzare questo codice.</span><span class="sxs-lookup"><span data-stu-id="5a580-279">Use this code.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public OperationDetails details;  
}  
  
[DataContract]  
public class OperationDetails  
{  
  [DataMember] public Account sourceAccount;  
  [DataMember] public Account targetAccount;  
  [DataMember] public int amount;  
}  
```  
  
### <a name="event-based-asynchronous-and-message-contracts"></a><span data-ttu-id="5a580-280">Contratti client e di messaggio asincroni basati su eventi</span><span class="sxs-lookup"><span data-stu-id="5a580-280">Event-based Asynchronous and Message Contracts</span></span>  
 <span data-ttu-id="5a580-281">Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="5a580-281">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="5a580-282">Di conseguenza, è possibile che, se un client importa metadati usando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="5a580-282">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="5a580-283">Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, usare l’opzione di comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="5a580-283">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="5a580-284">Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="5a580-284">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="5a580-285">Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="5a580-285">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a580-286">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a580-286">See also</span></span>

- [<span data-ttu-id="5a580-287">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="5a580-287">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="5a580-288">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="5a580-288">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
