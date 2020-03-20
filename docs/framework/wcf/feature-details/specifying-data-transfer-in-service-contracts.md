---
title: Specifica del trasferimento di dati nei contratti di servizio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
ms.openlocfilehash: e68ca46f9d2c562491063ae66754c469dbe0898e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184432"
---
# <a name="specifying-data-transfer-in-service-contracts"></a><span data-ttu-id="80170-102">Specifica del trasferimento di dati nei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="80170-102">Specifying Data Transfer in Service Contracts</span></span>
<span data-ttu-id="80170-103">Windows Communication Foundation (WCF) può essere considerato come un'infrastruttura di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="80170-103">The Windows Communication Foundation (WCF) can be thought of as a messaging infrastructure.</span></span> <span data-ttu-id="80170-104">Le operazioni di servizio possono ricevere, elaborare e inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="80170-104">Service operations can receive messages, process them, and send them messages.</span></span> <span data-ttu-id="80170-105">I messaggi vengono descritti tramite contratti di operazione.</span><span class="sxs-lookup"><span data-stu-id="80170-105">Messages are described using operation contracts.</span></span> <span data-ttu-id="80170-106">Si consideri ad esempio il contratto seguente:</span><span class="sxs-lookup"><span data-stu-id="80170-106">For example, consider the following contract.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(string fromCity, string toCity);  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
  
    <OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
End Interface  
```  
  
 <span data-ttu-id="80170-107">In questo contratto, l'operazione `GetAirfare` accetta un messaggio contenente le informazioni `fromCity` e `toCity` e quindi restituisce un messaggio che contiene un numero.</span><span class="sxs-lookup"><span data-stu-id="80170-107">Here, the `GetAirfare` operation accepts a message with information about `fromCity` and `toCity`, and then returns a message that contains a number.</span></span>  
  
 <span data-ttu-id="80170-108">In questo argomento vengono mostrati i vari modi in cui un contratto di operazione può descrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="80170-108">This topic explains the various ways in which an operation contract can describe messages.</span></span>  
  
## <a name="describing-messages-by-using-parameters"></a><span data-ttu-id="80170-109">Descrizione dei messaggi tramite parametri</span><span class="sxs-lookup"><span data-stu-id="80170-109">Describing Messages by Using Parameters</span></span>  
 <span data-ttu-id="80170-110">Il modo più semplice per descrivere un messaggio è utilizzare un elenco di parametri e il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="80170-110">The simplest way to describe a message is to use a parameter list and the return value.</span></span> <span data-ttu-id="80170-111">Nell'esempio precedente, i parametri stringa `fromCity` e `toCity` vengono utilizzati per descrivere il messaggio di richiesta, mentre il valore restituito float viene utilizzato per descrivere il messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="80170-111">In the preceding example, the `fromCity` and `toCity` string parameters were used to describe the request message, and the float return value was used to describe the reply message.</span></span> <span data-ttu-id="80170-112">Se il valore restituito non è sufficiente a descrivere un messaggio di risposta, è possibile utilizzare i parametri out.</span><span class="sxs-lookup"><span data-stu-id="80170-112">If the return value alone is not enough to describe a reply message, out parameters may be used.</span></span> <span data-ttu-id="80170-113">Ad esempio, l'operazione seguente contiene i parametri `fromCity` e `toCity` nel messaggio di richiesta e una coppia numero/valuta nel messaggio di risposta:</span><span class="sxs-lookup"><span data-stu-id="80170-113">For example, the following operation has `fromCity` and `toCity` in its request message, and a number together with a currency in its reply message:</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 <span data-ttu-id="80170-114">È inoltre possibile usare i parametri per riferimento di modo che un parametro appartenga sia al messaggio di richiesta sia al messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="80170-114">Additionally, you may use reference parameters to make a parameter part of both the request and the reply message.</span></span> <span data-ttu-id="80170-115">Il tipo dei parametri deve essere serializzabile, ovvero convertibile in XML.</span><span class="sxs-lookup"><span data-stu-id="80170-115">The parameters must be of types that can be serialized (converted to XML).</span></span> <span data-ttu-id="80170-116">Per impostazione predefinita, WCF <xref:System.Runtime.Serialization.DataContractSerializer> utilizza un componente denominato classe per eseguire questa conversione.</span><span class="sxs-lookup"><span data-stu-id="80170-116">By default, WCF uses a component called the <xref:System.Runtime.Serialization.DataContractSerializer> class to perform this conversion.</span></span> <span data-ttu-id="80170-117">Il sistema supporta la maggior parte dei tipi primitivi, ad esempio `int`, `string`, `float` e `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="80170-117">Most primitive types (such as `int`, `string`, `float`, and `DateTime`.) are supported.</span></span> <span data-ttu-id="80170-118">I tipi definiti dall'utente in genere devono presentare un contratto di dati.</span><span class="sxs-lookup"><span data-stu-id="80170-118">User-defined types must normally have a data contract.</span></span> <span data-ttu-id="80170-119">Per ulteriori informazioni, vedere [Utilizzo dei contratti dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="80170-119">For more information, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
```csharp
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
  
    [DataContract]  
    public class Itinerary  
    {  
        [DataMember]  
        public string fromCity;  
        [DataMember]  
        public string toCity;  
   }  
}  
```  
  
```vb  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
    <DataContract()>  
    Class Itinerary  
  
        <DataMember()>  
        Public fromCity As String  
        <DataMember()>  
        Public toCity As String  
    End Class  
End Interface  
```  
  
 <span data-ttu-id="80170-120">Talvolta il componente `DataContractSerializer` non è adatto per serializzare i tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="80170-120">Occasionally, the `DataContractSerializer` is not adequate to serialize your types.</span></span> <span data-ttu-id="80170-121">WCF supporta un motore di <xref:System.Xml.Serialization.XmlSerializer>serializzazione alternativo, il , che è possibile utilizzare anche per serializzare i parametri.</span><span class="sxs-lookup"><span data-stu-id="80170-121">WCF supports an alternative serialization engine, the <xref:System.Xml.Serialization.XmlSerializer>, which you can also use to serialize parameters.</span></span> <span data-ttu-id="80170-122">Gli attributi del motore <xref:System.Xml.Serialization.XmlSerializer>, ad esempio `XmlAttributeAttribute`, consentono di migliorare il controllo sul codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="80170-122">The <xref:System.Xml.Serialization.XmlSerializer> allows you to use more control over the resultant XML using attributes such as the `XmlAttributeAttribute`.</span></span> <span data-ttu-id="80170-123">Se si desidera attivare il motore <xref:System.Xml.Serialization.XmlSerializer> per una determinata operazione o per l'intero servizio, applicare l'attributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> a un'operazione o al servizio.</span><span class="sxs-lookup"><span data-stu-id="80170-123">To switch to using the <xref:System.Xml.Serialization.XmlSerializer> for a particular operation or for the entire service, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to an operation or a service.</span></span> <span data-ttu-id="80170-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="80170-124">For example:</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    [XmlSerializerFormat]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
}  
public class Itinerary  
{  
    public string fromCity;  
    public string toCity;  
    [XmlAttribute]  
    public bool isFirstClass;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    <XmlSerializerFormat>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
End Interface  
  
Class Itinerary  
  
    Public fromCity As String  
    Public toCity As String  
    <XmlSerializerFormat()>  
    Public isFirstClass As Boolean  
End Class  
```  
  
 <span data-ttu-id="80170-125">Per ulteriori informazioni, vedere [Utilizzo della classe XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span><span class="sxs-lookup"><span data-stu-id="80170-125">For more information, see [Using the XmlSerializer Class](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span></span> <span data-ttu-id="80170-126">Si tenga presente che è consigliabile evitare l'attivazione manuale del motore <xref:System.Xml.Serialization.XmlSerializer> appena illustrata, salvo nei casi specifici in cui questa attivazione sia effettivamente necessaria, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="80170-126">Remember that manually switching to the <xref:System.Xml.Serialization.XmlSerializer> as shown here is not recommended unless you have specific reasons to do so as detailed in that topic.</span></span>  
  
 <span data-ttu-id="80170-127">Per isolare i nomi di parametro .NET dai nomi di contratto è possibile utilizzare l'attributo <xref:System.ServiceModel.MessageParameterAttribute>. Per impostare i nomi di contratto è possibile utilizzare la proprietà `Name`.</span><span class="sxs-lookup"><span data-stu-id="80170-127">To isolate .NET parameter names from contract names, you can use the <xref:System.ServiceModel.MessageParameterAttribute> attribute, and use the `Name` property to set the contract name.</span></span> <span data-ttu-id="80170-128">Ad esempio, il contratto dell'operazione seguente è equivalente al primo esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="80170-128">For example, the following operation contract is equivalent to the first example in this topic.</span></span>  
  
```csharp  
[OperationContract]  
public float GetAirfare(  
    [MessageParameter(Name="fromCity")] string originCity,  
    [MessageParameter(Name="toCity")] string destinationCity);  
```  
  
```vb  
<OperationContract()>  
  Function GetAirfare(<MessageParameter(Name := "fromCity")> fromCity As String, <MessageParameter(Name := "toCity")> toCity As String) As Double  
```  
  
## <a name="describing-empty-messages"></a><span data-ttu-id="80170-129">Descrizione dei messaggi vuoti</span><span class="sxs-lookup"><span data-stu-id="80170-129">Describing Empty Messages</span></span>  
 <span data-ttu-id="80170-130">Per descrivere un messaggio di richiesta vuoto è possibile non specificare alcun parametro per riferimento o di input.</span><span class="sxs-lookup"><span data-stu-id="80170-130">An empty request message can be described by having no input or reference parameters.</span></span> <span data-ttu-id="80170-131">Ad esempio, in C:</span><span class="sxs-lookup"><span data-stu-id="80170-131">For example, in C#:</span></span>  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 <span data-ttu-id="80170-132">Ad esempio, in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="80170-132">For example, in Visual Basic:</span></span>  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 <span data-ttu-id="80170-133">Per descrivere un messaggio di risposta vuoto è possibile utilizzare un tipo restituito `void` e non specificare alcun parametro referenziato o di output.</span><span class="sxs-lookup"><span data-stu-id="80170-133">An empty reply message can be described by having a `void` return type and no output or reference parameters.</span></span> <span data-ttu-id="80170-134">Ad esempio in:</span><span class="sxs-lookup"><span data-stu-id="80170-134">For example in:</span></span>  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 <span data-ttu-id="80170-135">Si noti che questa operazione è diversa da un'operazione unidirezionale:</span><span class="sxs-lookup"><span data-stu-id="80170-135">This is different from a one-way operation, such as:</span></span>  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 <span data-ttu-id="80170-136">L'operazione `SetTemperatureStatus` restituisce un messaggio vuoto e,</span><span class="sxs-lookup"><span data-stu-id="80170-136">The `SetTemperatureStatus` operation returns an empty message.</span></span> <span data-ttu-id="80170-137">se si verifica un problema durante l'elaborazione del messaggio di input, può restituire un errore.</span><span class="sxs-lookup"><span data-stu-id="80170-137">It may return a fault instead if there is a problem processing the input message.</span></span> <span data-ttu-id="80170-138">L'operazione `SetLightbulbStatus` non restituisce invece alcun valore</span><span class="sxs-lookup"><span data-stu-id="80170-138">The `SetLightbulbStatus` operation returns nothing.</span></span> <span data-ttu-id="80170-139">e non è in grado di segnalare il verificarsi di una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="80170-139">There is no way to communicate a fault condition from this operation.</span></span>  
  
## <a name="describing-messages-by-using-message-contracts"></a><span data-ttu-id="80170-140">Descrizione dei messaggi tramite i contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="80170-140">Describing Messages by Using Message Contracts</span></span>  
 <span data-ttu-id="80170-141">In alcuni casi conviene utilizzare un unico tipo per rappresentare un intero messaggio.</span><span class="sxs-lookup"><span data-stu-id="80170-141">You may want to use a single type to represent the entire message.</span></span> <span data-ttu-id="80170-142">Benché a tale scopo sia possibile utilizzare un contratto di dati, è comunque consigliabile utilizzare un contratto di messaggio. Questo approccio consente infatti di evitare livelli di wrapping superflui nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="80170-142">While it is possible to use a data contract for this purpose, the recommended way to do this is to use a message contract—this avoids unnecessary levels of wrapping in the resultant XML.</span></span> <span data-ttu-id="80170-143">Inoltre, i contratti di messaggio consentono di migliorare il controllo sui messaggi risultanti.</span><span class="sxs-lookup"><span data-stu-id="80170-143">Additionally, message contracts allow you to exercise more control over resultant messages.</span></span> <span data-ttu-id="80170-144">È ad esempio possibile definire in modo specifico i tipi di informazione contenuti nel corpo e nelle intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="80170-144">For instance, you can decide which pieces of information should be in the message body and which should be in the message headers.</span></span> <span data-ttu-id="80170-145">Nell'esempio seguente viene illustrato l'utilizzo dei contratti di messaggio.</span><span class="sxs-lookup"><span data-stu-id="80170-145">The following example shows the use of message contracts.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    GetAirfareResponse GetAirfare(GetAirfareRequest request);  
}  
  
[MessageContract]  
public class GetAirfareRequest  
{  
    [MessageHeader] public DateTime date;  
    [MessageBodyMember] public Itinerary itinerary;  
}  
  
[MessageContract]  
public class GetAirfareResponse  
{  
    [MessageBodyMember] public float airfare;  
    [MessageBodyMember] public string currency;  
}  
  
[DataContract]  
public class Itinerary  
{  
    [DataMember] public string fromCity;  
    [DataMember] public string toCity;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    Function GetAirfare(request As GetAirfareRequest) As GetAirfareResponse  
End Interface  
  
<MessageContract()>  
Public Class GetAirfareRequest  
    <MessageHeader()>
    Public Property date as DateTime  
    <MessageBodyMember()>  
    Public Property itinerary As Itinerary  
End Class  
  
<MessageContract()>  
Public Class GetAirfareResponse  
    <MessageBodyMember()>  
    Public Property airfare As Double  
    <MessageBodyMember()> Public Property currency As String  
End Class  
  
<DataContract()>  
Public Class Itinerary  
    <DataMember()> Public Property fromCity As String  
    <DataMember()> Public Property toCity As String  
End Class  
```  
  
 <span data-ttu-id="80170-146">Per ulteriori informazioni, vedere [Utilizzo dei contratti](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)di messaggio .</span><span class="sxs-lookup"><span data-stu-id="80170-146">For more information, see [Using Message Contracts](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
 <span data-ttu-id="80170-147">Nell'esempio precedente la classe <xref:System.Runtime.Serialization.DataContractSerializer> viene utilizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="80170-147">In the previous example, the <xref:System.Runtime.Serialization.DataContractSerializer> class is still used by default.</span></span> <span data-ttu-id="80170-148">Nei contratti di messaggio è inoltre possibile utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-148">The <xref:System.Xml.Serialization.XmlSerializer> class can also be used with message contracts.</span></span> <span data-ttu-id="80170-149">A tale scopo, applicare l'attributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> all'operazione oppure al contratto e quindi utilizzare tipi compatibili con la classe <xref:System.Xml.Serialization.XmlSerializer> nei membri delle intestazioni e del corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="80170-149">To do this, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to either the operation or the contract, and use types compatible with the <xref:System.Xml.Serialization.XmlSerializer> class in the message headers and body members.</span></span>  
  
## <a name="describing-messages-by-using-streams"></a><span data-ttu-id="80170-150">Descrizione dei messaggi tramite flussi</span><span class="sxs-lookup"><span data-stu-id="80170-150">Describing Messages by Using Streams</span></span>  
 <span data-ttu-id="80170-151">Un altro modo per descrivere i messaggi nelle operazioni consiste nell'utilizzare la classe <xref:System.IO.Stream> o una delle relative classi derivate in un contratto di operazione oppure come membro del corpo del contratto di messaggio. In quest'ultimo caso è necessario che questo membro sia l'unico.</span><span class="sxs-lookup"><span data-stu-id="80170-151">Another way to describe messages in operations is to use the <xref:System.IO.Stream> class or one of its derived classes in an operation contract or as a message contract body member (it must be the only member in this case).</span></span> <span data-ttu-id="80170-152">Per i messaggi in ingresso, il tipo deve essere `Stream`. Non è consentito l'utilizzo di classi derivate.</span><span class="sxs-lookup"><span data-stu-id="80170-152">For incoming messages, the type must be `Stream`—you cannot use derived classes.</span></span>  
  
 <span data-ttu-id="80170-153">Anziché richiamare il serializzatore, WCF recupera i dati da un flusso e li inserisce direttamente in un messaggio in uscita o recupera i dati da un messaggio in arrivo e li inserisce direttamente in un flusso.</span><span class="sxs-lookup"><span data-stu-id="80170-153">Instead of invoking the serializer, WCF retrieves data from a stream and puts it directly into an outgoing message, or retrieves data from an incoming message and puts it directly into a stream.</span></span> <span data-ttu-id="80170-154">Nell'esempio seguente viene illustrato l'utilizzo dei flussi.</span><span class="sxs-lookup"><span data-stu-id="80170-154">The following sample shows the use of streams.</span></span>  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 <span data-ttu-id="80170-155">Non è consentito combinare dati `Stream` e dati non di flusso in un unico corpo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="80170-155">You cannot combine `Stream` and non-stream data in a single message body.</span></span> <span data-ttu-id="80170-156">Per aggiungere altri dati nelle intestazioni di messaggio è necessario utilizzare un contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="80170-156">Use a message contract to put the extra data in message headers.</span></span> <span data-ttu-id="80170-157">Nell'esempio seguente viene mostrato un utilizzo non corretto dei flussi quando si definisce un contratto di operazione.</span><span class="sxs-lookup"><span data-stu-id="80170-157">The following example shows the incorrect usage of streams when defining the operation contract.</span></span>  
  
```csharp  
//Incorrect:  
// [OperationContract]  
// public void UploadFile (string fileName, Stream fileData);  
```  
  
```vb  
'Incorrect:  
    '<OperationContract()>  
    Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
```  
  
 <span data-ttu-id="80170-158">Nell'esempio seguente viene mostrato un utilizzo corretto dei flussi quando si definisce un contratto di operazione.</span><span class="sxs-lookup"><span data-stu-id="80170-158">The following sample shows the correct usage of streams when defining an operation contract.</span></span>  
  
```csharp  
[OperationContract]  
public void UploadFile (UploadFileMessage message);  
//code omitted  
[MessageContract]  
public class UploadFileMessage  
{  
    [MessageHeader] public string fileName;  
    [MessageBodyMember] public Stream fileData;  
}  
```  
  
```vb  
<OperationContract()>  
Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
'Code Omitted  
<MessageContract()>  
Public Class UploadFileMessage  
   <MessageHeader()>  
    Public Property fileName As String  
    <MessageBodyMember()>  
    Public Property fileData As Stream  
End Class  
```  
  
 <span data-ttu-id="80170-159">Per ulteriori informazioni, vedere [Dati di grandi dimensioni e Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).</span><span class="sxs-lookup"><span data-stu-id="80170-159">For more information, see [Large Data and Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="using-the-message-class"></a><span data-ttu-id="80170-160">Utilizzo della classe Message</span><span class="sxs-lookup"><span data-stu-id="80170-160">Using the Message Class</span></span>  
 <span data-ttu-id="80170-161">Per controllare in modo completo a livello di codice lo scambio dei messaggi è possibile utilizzare direttamente la classe <xref:System.ServiceModel.Channels.Message>, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80170-161">To have complete programmatic control over messages sent or received, you can use the <xref:System.ServiceModel.Channels.Message> class directly, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 <span data-ttu-id="80170-162">Si tratta di uno scenario avanzato, descritto in dettaglio in [Utilizzo della classe messaggio](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).</span><span class="sxs-lookup"><span data-stu-id="80170-162">This is an advanced scenario, which is described in detail in [Using the Message Class](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).</span></span>  
  
## <a name="describing-fault-messages"></a><span data-ttu-id="80170-163">Descrizione dei messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="80170-163">Describing Fault Messages</span></span>  
 <span data-ttu-id="80170-164">Oltre ai messaggi descritti in base al valore restituito e ai parametri per riferimento o di output, qualsiasi operazione non unidirezionale può restituire almeno due messaggi: il messaggio di risposta normale e un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="80170-164">In addition to the messages that are described by the return value and output or reference parameters, any operation that is not one-way can return at least two possible messages: its normal response message and a fault message.</span></span> <span data-ttu-id="80170-165">Si consideri il contratto di operazione seguente.</span><span class="sxs-lookup"><span data-stu-id="80170-165">Consider the following operation contract.</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 <span data-ttu-id="80170-166">Questa operazione può restituire un messaggio normale contenente un numero `float` o un messaggio di errore contenente un codice di errore e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="80170-166">This operation may either return a normal message that contains a `float` number, or a fault message that contains a fault code and a description.</span></span> <span data-ttu-id="80170-167">A tale scopo è possibile generare un'eccezione <xref:System.ServiceModel.FaultException> nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="80170-167">You can accomplish this by throwing a <xref:System.ServiceModel.FaultException> in your service implementation.</span></span>  
  
 <span data-ttu-id="80170-168">Per specificare eventuali messaggi di errore aggiuntivi è possibile utilizzare l'attributo <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80170-168">You can specify additional possible fault messages by using the <xref:System.ServiceModel.FaultContractAttribute> attribute.</span></span> <span data-ttu-id="80170-169">Gli errori aggiuntivi devono essere serializzabili tramite il componente <xref:System.Runtime.Serialization.DataContractSerializer>, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80170-169">The additional faults must be serializable using the <xref:System.Runtime.Serialization.DataContractSerializer>, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
[FaultContract(typeof(ItineraryNotAvailableFault))]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
  
//code omitted  
  
[DataContract]  
public class ItineraryNotAvailableFault  
{  
    [DataMember]  
    public bool IsAlternativeDateAvailable;  
  
    [DataMember]  
    public DateTime alternativeSuggestedDate;  
}  
```  
  
```vb  
<OperationContract()>  
<FaultContract(GetType(ItineraryNotAvailableFault))>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime) As Double  
  
'Code Omitted  
<DataContract()>  
Public Class  
  <DataMember()>  
  Public Property IsAlternativeDateAvailable As Boolean  
  <DataMember()>  
  Public Property alternativeSuggestedDate As DateTime  
End Class  
```  
  
 <span data-ttu-id="80170-170">Questi errori aggiuntivi possono essere generati mediante un'eccezione <xref:System.ServiceModel.FaultException%601> del tipo di contratto di dati appropriato.</span><span class="sxs-lookup"><span data-stu-id="80170-170">These additional faults can be generated by throwing a <xref:System.ServiceModel.FaultException%601> of the appropriate data contract type.</span></span> <span data-ttu-id="80170-171">Per ulteriori informazioni, vedere [Gestione di eccezioni ed errori](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span><span class="sxs-lookup"><span data-stu-id="80170-171">For more information, see [Handling Exceptions and Faults](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span></span>  
  
 <span data-ttu-id="80170-172">Non è consentito utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer> per descrivere errori.</span><span class="sxs-lookup"><span data-stu-id="80170-172">You cannot use the <xref:System.Xml.Serialization.XmlSerializer> class to describe faults.</span></span> <span data-ttu-id="80170-173">L'attributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> non ha alcun effetto sui messaggi di errore di un contratto.</span><span class="sxs-lookup"><span data-stu-id="80170-173">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> has no effect on fault contracts.</span></span>  
  
## <a name="using-derived-types"></a><span data-ttu-id="80170-174">Utilizzo di tipi derivati</span><span class="sxs-lookup"><span data-stu-id="80170-174">Using Derived Types</span></span>  
 <span data-ttu-id="80170-175">In alcuni casi conviene utilizzare un tipo di base in un'operazione o in un contratto di messaggio e quindi utilizzare un tipo derivato per richiamare effettivamente l'operazione.</span><span class="sxs-lookup"><span data-stu-id="80170-175">You may want to use a base type in an operation or a message contract, and then use a derived type when actually invoking the operation.</span></span> <span data-ttu-id="80170-176">In questi casi è necessario utilizzare l'attributo <xref:System.ServiceModel.ServiceKnownTypeAttribute> oppure un meccanismo alternativo per consentire l'utilizzo di tipi derivati.</span><span class="sxs-lookup"><span data-stu-id="80170-176">In this case, you must use either the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute or some alternative mechanism to allow the use of derived types.</span></span> <span data-ttu-id="80170-177">Si consideri l'operazione seguente.</span><span class="sxs-lookup"><span data-stu-id="80170-177">Consider the following operation.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 <span data-ttu-id="80170-178">Si supponga che due tipi, `Book` e `Magazine`, derivino dal tipo `LibraryItem`.</span><span class="sxs-lookup"><span data-stu-id="80170-178">Assume that two types, `Book` and `Magazine`, derive from `LibraryItem`.</span></span> <span data-ttu-id="80170-179">Per utilizzare questi tipi nell'operazione `IsLibraryItemAvailable` è possibile modificare l'operazione come segue:</span><span class="sxs-lookup"><span data-stu-id="80170-179">To use these types in the `IsLibraryItemAvailable` operation, you can change the operation as follows:</span></span>  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 <span data-ttu-id="80170-180">In alternativa, quando si utilizza il componente <xref:System.Runtime.Serialization.KnownTypeAttribute> predefinito, è possibile utilizzare l'attributo <xref:System.Runtime.Serialization.DataContractSerializer>, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80170-180">Alternatively, you can use the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute when the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
  
// code omitted
  
[DataContract]  
[KnownType(typeof(Book))]  
[KnownType(typeof(Magazine))]  
public class LibraryItem  
{  
    //code omitted  
}  
```  
  
```vb  
<OperationContract()>  
Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
  
'Code Omitted  
<DataContract()>  
<KnownType(GetType(Book))>  
<KnownType(GetType(Magazine))>  
Public Class LibraryItem  
  'Code Omitted  
End Class  
```  
  
 <span data-ttu-id="80170-181">Quando invece si utilizza il motore <xref:System.Xml.Serialization.XmlIncludeAttribute> è possibile utilizzare l'attributo <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-181">You can use the <xref:System.Xml.Serialization.XmlIncludeAttribute> attribute when using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
 <span data-ttu-id="80170-182">L'attributo <xref:System.ServiceModel.ServiceKnownTypeAttribute> può essere applicato a un'operazione specifica o all'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="80170-182">You can apply the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute to an operation or to the entire service.</span></span> <span data-ttu-id="80170-183">Analogamente all'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute>, tale attributo accetta un tipo o il nome del metodo da chiamare per ottenere un elenco di tipi noti.</span><span class="sxs-lookup"><span data-stu-id="80170-183">It accepts either a type or the name of the method to call to get a list of known types, just like the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span> <span data-ttu-id="80170-184">Per ulteriori informazioni, vedere [Tipi noti di contratti dati](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="80170-184">For more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="specifying-the-use-and-style"></a><span data-ttu-id="80170-185">Specifica delle proprietà Use e Style</span><span class="sxs-lookup"><span data-stu-id="80170-185">Specifying the Use and Style</span></span>  
 <span data-ttu-id="80170-186">I due stili più comunemente utilizzati per descrivere i servizi tramite Web Services Description Language (WSDL) sono Document e Remote Procedure Call (RPC).</span><span class="sxs-lookup"><span data-stu-id="80170-186">When describing services using Web Services Description Language (WSDL), the two commonly used styles are Document and remote procedure call (RPC).</span></span> <span data-ttu-id="80170-187">Nello stile Document, l'intero corpo del messaggio viene descritto utilizzando un unico schema e WSDL descrive le varie parti del corpo del messaggio facendo riferimento agli elementi di tale schema.</span><span class="sxs-lookup"><span data-stu-id="80170-187">In the Document style, the entire message body is described using the schema, and the WSDL describes the various message body parts by referring to elements within that schema.</span></span> <span data-ttu-id="80170-188">Nello stile RPC, invece, WSDL descrive le varie parti del corpo del messaggio facendo riferimento a vari tipi di schema.</span><span class="sxs-lookup"><span data-stu-id="80170-188">In the RPC style, the WSDL refers to a schema type for each message part rather than an element.</span></span> <span data-ttu-id="80170-189">In alcuni casi occorre selezionare manualmente uno di questi stili.</span><span class="sxs-lookup"><span data-stu-id="80170-189">In some cases, you have to manually select one of these styles.</span></span> <span data-ttu-id="80170-190">A tale scopo è possibile applicare l'attributo <xref:System.ServiceModel.DataContractFormatAttribute> e impostare la proprietà `Style` (quando si utilizza il componente <xref:System.Runtime.Serialization.DataContractSerializer>) oppure impostare la proprietà `Style` dell'attributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> (quando si utilizza il motore <xref:System.Xml.Serialization.XmlSerializer>).</span><span class="sxs-lookup"><span data-stu-id="80170-190">You can do this by applying the <xref:System.ServiceModel.DataContractFormatAttribute> attribute and setting the `Style` property (when the <xref:System.Runtime.Serialization.DataContractSerializer> is in use), or by setting `Style` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute (when using the <xref:System.Xml.Serialization.XmlSerializer>).</span></span>  
  
 <span data-ttu-id="80170-191">Inoltre, l'oggetto <xref:System.Xml.Serialization.XmlSerializer> supporta due formati di XML serializzato: `Literal` e `Encoded`.</span><span class="sxs-lookup"><span data-stu-id="80170-191">Additionally, the <xref:System.Xml.Serialization.XmlSerializer> supports two forms of serialized XML: `Literal` and `Encoded`.</span></span> <span data-ttu-id="80170-192">`Literal` è il formato in genere più accettato ed è l'unico a essere supportato da <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-192">`Literal` is the most commonly accepted form, and is the only form the <xref:System.Runtime.Serialization.DataContractSerializer> supports.</span></span> <span data-ttu-id="80170-193">`Encoded` è un formato legacy descritto nella sezione 5 della specifica SOAP ed è consigliabile evitarne l'utilizzo nei servizi più recenti.</span><span class="sxs-lookup"><span data-stu-id="80170-193">`Encoded` is a legacy form described in section 5 of the SOAP specification, and is not recommended for new services.</span></span> <span data-ttu-id="80170-194">Per passare alla modalità `Encoded`, impostare la proprietà `Use` dell'attributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> su `Encoded`.</span><span class="sxs-lookup"><span data-stu-id="80170-194">To switch to `Encoded` mode, set the `Use` property on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to `Encoded`.</span></span>  
  
 <span data-ttu-id="80170-195">Nella maggior parte dei casi è consigliabile evitare di modificare le impostazioni predefinite delle proprietà `Style` e `Use`.</span><span class="sxs-lookup"><span data-stu-id="80170-195">In most cases, you should not change the default settings for the `Style` and `Use` properties.</span></span>  
  
## <a name="controlling-the-serialization-process"></a><span data-ttu-id="80170-196">Controllo del processo di serializzazione</span><span class="sxs-lookup"><span data-stu-id="80170-196">Controlling the Serialization Process</span></span>  
 <span data-ttu-id="80170-197">Sono disponibili diversi modi per personalizzare il processo di serializzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="80170-197">You can do a number of things to customize the way data is serialized.</span></span>  
  
### <a name="changing-server-serialization-settings"></a><span data-ttu-id="80170-198">Modifica delle impostazioni di serializzazione del server</span><span class="sxs-lookup"><span data-stu-id="80170-198">Changing Server Serialization Settings</span></span>  
 <span data-ttu-id="80170-199">Quando si utilizza il componente <xref:System.Runtime.Serialization.DataContractSerializer> predefinito è possibile controllare alcuni aspetti del processo di serializzazione del servizio. A tale scopo è possibile applicare l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> al servizio.</span><span class="sxs-lookup"><span data-stu-id="80170-199">When the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, you can control some aspects of the serialization process on the service by applying the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the service.</span></span> <span data-ttu-id="80170-200">In particolare, è possibile utilizzare la proprietà `MaxItemsInObjectGraph` per impostare la quota che limita il numero massimo di oggetti deserializzati dal componente <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-200">Specifically, you may use the `MaxItemsInObjectGraph` property to set the quota that limits the maximum number of objects the <xref:System.Runtime.Serialization.DataContractSerializer> deserializes.</span></span> <span data-ttu-id="80170-201">È possibile utilizzare la proprietà `IgnoreExtensionDataObject` per disattivare la funzionalità di controllo delle versioni delle sequenze di andata e ritorno.</span><span class="sxs-lookup"><span data-stu-id="80170-201">You can use the `IgnoreExtensionDataObject` property to turn off the round-tripping versioning feature.</span></span> <span data-ttu-id="80170-202">Per altre informazioni sulle quote, vedere [Considerazioni sulla protezione per i dati](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span><span class="sxs-lookup"><span data-stu-id="80170-202">For more information about quotas, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span> <span data-ttu-id="80170-203">Per ulteriori informazioni sul round trip, vedere [Contratti dati compatibili con](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)le future dimensioni .</span><span class="sxs-lookup"><span data-stu-id="80170-203">For more information about round-tripping, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
```csharp  
[ServiceBehavior(MaxItemsInObjectGraph=100000)]  
public class MyDataService:IDataService  
{  
    public DataPoint[] GetData()  
    {  
       // Implementation omitted  
    }  
}  
```  
  
```vb  
<ServiceBehavior(MaxItemsInObjectGraph:=100000)>  
Public Class MyDataService Implements IDataService  
  
    Function GetData() As DataPoint()  
         ‘ Implementation omitted  
    End Function  
End Interface  
```  
  
### <a name="serialization-behaviors"></a><span data-ttu-id="80170-204">Comportamenti di serializzazione</span><span class="sxs-lookup"><span data-stu-id="80170-204">Serialization Behaviors</span></span>  
 <span data-ttu-id="80170-205">In WCF sono disponibili due <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> comportamenti, e <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> che vengono inseriti automaticamente a seconda del serializzatore in uso per una determinata operazione.</span><span class="sxs-lookup"><span data-stu-id="80170-205">Two behaviors are available in WCF, the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> and the <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> that are automatically plugged in depending on which serializer is in use for a particular operation.</span></span> <span data-ttu-id="80170-206">Poiché questi comportamenti vengono attivati automaticamente, in genere non è necessario gestirli.</span><span class="sxs-lookup"><span data-stu-id="80170-206">Because these behaviors are applied automatically, you normally do not have to be aware of them.</span></span>  
  
 <span data-ttu-id="80170-207">Tuttavia, le proprietà `DataContractSerializerOperationBehavior`, `MaxItemsInObjectGraph` e `IgnoreExtensionDataObject` del comportamento `DataContractSurrogate` possono essere utilizzate per personalizzare il processo di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="80170-207">However, the `DataContractSerializerOperationBehavior` has the `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject`, and `DataContractSurrogate` properties that you may use to customize the serialization process.</span></span> <span data-ttu-id="80170-208">Come indicato nella sezione precedente, le prime due proprietà presentano lo stesso significato.</span><span class="sxs-lookup"><span data-stu-id="80170-208">The first two properties have the same meaning as discussed in the previous section.</span></span> <span data-ttu-id="80170-209">La proprietà `DataContractSurrogate` può essere utilizzata per abilitare i surrogati di contratti di dati, ovvero un meccanismo avanzato di personalizzazione ed estensione del processo di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="80170-209">You can use the `DataContractSurrogate` property to enable data contract surrogates, which are a powerful mechanism for customizing and extending the serialization process.</span></span> <span data-ttu-id="80170-210">Per ulteriori informazioni, vedere [Surrogati del contratto dati](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).</span><span class="sxs-lookup"><span data-stu-id="80170-210">For more information, see [Data Contract Surrogates](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).</span></span>  
  
 <span data-ttu-id="80170-211">La proprietà `DataContractSerializerOperationBehavior` consente di personalizzare la serializzazione sia del client sia del server.</span><span class="sxs-lookup"><span data-stu-id="80170-211">You can use the `DataContractSerializerOperationBehavior` to customize both client and server serialization.</span></span> <span data-ttu-id="80170-212">Nell'esempio seguente viene illustrato come aumentare la quota `MaxItemsInObjectGraph` del client.</span><span class="sxs-lookup"><span data-stu-id="80170-212">The following example shows how to increase the `MaxItemsInObjectGraph` quota on the client.</span></span>  
  
```csharp  
ChannelFactory<IDataService> factory = new ChannelFactory<IDataService>(binding, address);  
foreach (OperationDescription op in factory.Endpoint.Contract.Operations)  
{  
    DataContractSerializerOperationBehavior dataContractBehavior =  
                op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
    if (dataContractBehavior != null)  
    {  
        dataContractBehavior.MaxItemsInObjectGraph = 100000;  
    }  
}  
IDataService client = factory.CreateChannel();  
```  
  
```vb  
Dim factory As ChannelFactory(Of IDataService) = New ChannelFactory(Of IDataService)(binding, address)  
For Each op As OperationDescription In factory.Endpoint.Contract.Operations  
        Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
        If dataContractBehavior IsNot Nothing Then  
            dataContractBehavior.MaxItemsInObjectGraph = 100000  
        End If  
     Next  
    Dim client As IDataService = factory.CreateChannel  
```  
  
<span data-ttu-id="80170-213">Di seguito è riportato il codice equivalente nel servizio, nel caso self-hosted:The following is the equivalent code on the service, in the self-hosted case:</span><span class="sxs-lookup"><span data-stu-id="80170-213">The following is the equivalent code on the service, in the self-hosted case:</span></span>
  
```csharp  
ServiceHost serviceHost = new ServiceHost(typeof(IDataService))  
foreach (ServiceEndpoint ep in serviceHost.Description.Endpoints)  
{  
foreach (OperationDescription op in ep.Contract.Operations)  
{  
        DataContractSerializerOperationBehavior dataContractBehavior =  
           op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
        if (dataContractBehavior != null)  
        {  
            dataContractBehavior.MaxItemsInObjectGraph = 100000;  
        }  
}  
}  
serviceHost.Open();  
```  
  
```vb  
Dim serviceHost As ServiceHost = New ServiceHost(GetType(IDataService))  
        For Each ep As ServiceEndpoint In serviceHost.Description.Endpoints  
            For Each op As OperationDescription In ep.Contract.Operations  
                Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
  
                If dataContractBehavior IsNot Nothing Then  
                    dataContractBehavior.MaxItemsInObjectGraph = 100000  
                End If  
            Next  
        Next  
        serviceHost.Open()  
```  
  
 <span data-ttu-id="80170-214">Nel caso di servizio ospitato su Web è invece necessario creare una nuova classe derivata `ServiceHost` e utilizzare una factory di host del servizio per attivarla.</span><span class="sxs-lookup"><span data-stu-id="80170-214">In the Web-hosted case, you must create a new `ServiceHost` derived class and use a service host factory to plug it in.</span></span>  
  
### <a name="controlling-serialization-settings-in-configuration"></a><span data-ttu-id="80170-215">Controllo delle impostazioni di serializzazione in configurazione</span><span class="sxs-lookup"><span data-stu-id="80170-215">Controlling Serialization Settings in Configuration</span></span>  
 <span data-ttu-id="80170-216">Le proprietà `MaxItemsInObjectGraph` e `IgnoreExtensionDataObject` possono essere controllate in configurazione tramite il comportamento di endpoint o di servizio del componente `dataContractSerializer`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="80170-216">The `MaxItemsInObjectGraph` and `IgnoreExtensionDataObject` can be controlled through configuration by using the `dataContractSerializer` endpoint or service behavior, as shown in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="LargeQuotaBehavior">  
                    <dataContractSerializer  
                      maxItemsInObjectGraph="100000" />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <client>  
            <endpoint address="http://example.com/myservice"  
                  behaviorConfiguration="LargeQuotaBehavior"  
                binding="basicHttpBinding" bindingConfiguration=""
                            contract="IDataService"  
                name="" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a><span data-ttu-id="80170-217">Serializzazione con condivisione di tipi, conservazione degli oggetti grafici e serializzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="80170-217">Shared Type Serialization, Object Graph Preservation, and Custom Serializers</span></span>  
 <span data-ttu-id="80170-218">La serializzazione eseguita dal componente <xref:System.Runtime.Serialization.DataContractSerializer> si basa su nomi di contratto di dati e non su nomi di tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="80170-218">The <xref:System.Runtime.Serialization.DataContractSerializer> serializes using data contract names and not .NET type names.</span></span> <span data-ttu-id="80170-219">Ciò è in linea con i concetti di base dell'architettura orientata ai servizi e offre inoltre un elevato livello di flessibilità, in quanto i tipi .NET possono cambiare senza influire sul contratto di transito.</span><span class="sxs-lookup"><span data-stu-id="80170-219">This is consistent with service-oriented architecture tenets and allows for a great degree of flexibility—the .NET types can change without affecting the wire contract.</span></span> <span data-ttu-id="80170-220">In casi rari può risultare utile serializzare i nomi di tipo .NET effettivi. Questo approccio, analogamente alla tecnologia .NET Framework Remoting, comporta l'introduzione di un accoppiamento stretto fra client e server.</span><span class="sxs-lookup"><span data-stu-id="80170-220">In rare cases, you may want to serialize actual .NET type names, thereby introducing a tight coupling between the client and the server, similar to the .NET Framework remoting technology.</span></span> <span data-ttu-id="80170-221">Questa non è una procedura consigliata, tranne in rari casi che in genere si verificano durante la migrazione a WCF dai servizi remoti di .NET Framework.This is not a recommended practice, except in rare cases that usually occur when migrating to WCF from .NET Framework remoting.</span><span class="sxs-lookup"><span data-stu-id="80170-221">This is not a recommended practice, except in rare cases that usually occur when migrating to WCF from .NET Framework remoting.</span></span> <span data-ttu-id="80170-222">In questo caso è necessario utilizzare la classe <xref:System.Runtime.Serialization.NetDataContractSerializer> anziché la classe <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-222">In this case, you must use the <xref:System.Runtime.Serialization.NetDataContractSerializer> class instead of the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 <span data-ttu-id="80170-223">In genere il componente <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti grafici come oggetti struttura.</span><span class="sxs-lookup"><span data-stu-id="80170-223">The <xref:System.Runtime.Serialization.DataContractSerializer> normally serializes object graphs as object trees.</span></span> <span data-ttu-id="80170-224">Ovvero, se esistono più riferimenti a uno stesso oggetto, quest'ultimo viene serializzato più volte.</span><span class="sxs-lookup"><span data-stu-id="80170-224">That is, if the same object is referred to more than once, it is serialized more than once.</span></span> <span data-ttu-id="80170-225">Si consideri ad esempio il caso di un'istanza della classe `PurchaseOrder` contenente i campi `billTo` e `shipTo` di tipo Address.</span><span class="sxs-lookup"><span data-stu-id="80170-225">For example, consider a `PurchaseOrder` instance that has two fields of type Address called `billTo` and `shipTo`.</span></span> <span data-ttu-id="80170-226">Se entrambi i campi vengono impostati sulla stessa istanza di Address, dopo la serializzazione e la deserializzazione esistono due istanze identiche di Address.</span><span class="sxs-lookup"><span data-stu-id="80170-226">If both fields are set to the same Address instance, there are two identical Address instances after serialization and deserialization.</span></span> <span data-ttu-id="80170-227">Ciò è dovuto al fatto che non esiste alcuna modalità standard interoperativa per rappresentare gli oggetti grafici in XML, salvo nel caso dello standard legacy con codifica SOAP disponibile nel motore <xref:System.Xml.Serialization.XmlSerializer>, come descritto nella sezione precedente relativa alle proprietà `Style` e `Use`.</span><span class="sxs-lookup"><span data-stu-id="80170-227">This is done because there is no standard interoperable way to represent object graphs in XML (except for the legacy SOAP encoded standard available on the <xref:System.Xml.Serialization.XmlSerializer>, as described in the previous section on `Style` and `Use`).</span></span> <span data-ttu-id="80170-228">La serializzazione degli oggetti grafici come alberi comporta alcuni svantaggi. Ad esempio, risulta impossibile serializzare i grafici aventi riferimenti circolari.</span><span class="sxs-lookup"><span data-stu-id="80170-228">Serializing object graphs as trees has certain disadvantages, for example, graphs with circular references cannot be serialized.</span></span> <span data-ttu-id="80170-229">Talvolta occorre attivare la serializzazione degli oggetti grafici, anche se non è interoperativa.</span><span class="sxs-lookup"><span data-stu-id="80170-229">Occasionally, it is necessary to switch to true object graph serialization, even though it is not interoperable.</span></span> <span data-ttu-id="80170-230">A tale scopo è possibile utilizzare il componente <xref:System.Runtime.Serialization.DataContractSerializer> costruito con il parametro `preserveObjectReferences` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="80170-230">This can be done by using the <xref:System.Runtime.Serialization.DataContractSerializer> constructed with the `preserveObjectReferences` parameter set to `true`.</span></span>  
  
 <span data-ttu-id="80170-231">Talvolta i serializzatori incorporati risultano insufficienti per lo scenario da gestire.</span><span class="sxs-lookup"><span data-stu-id="80170-231">Occasionally, the built-in serializers are not enough for your scenario.</span></span> <span data-ttu-id="80170-232">Nella maggior parte dei casi è comunque possibile utilizzare l'astrazione <xref:System.Runtime.Serialization.XmlObjectSerializer> dalla quale derivano sia il serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> sia il serializzatore <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-232">In most cases, you can still use the <xref:System.Runtime.Serialization.XmlObjectSerializer> abstraction from which both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Runtime.Serialization.NetDataContractSerializer> derive.</span></span>  
  
 <span data-ttu-id="80170-233">Per tutti e tre i casi precedenti (conservazione dei tipi .NET, conservazione degli oggetti grafici e serializzazione completamente personalizzata basata su `XmlObjectSerializer`) è necessario attivare un serializzatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="80170-233">The previous three cases (.NET type preservation, object graph preservation, and completely custom `XmlObjectSerializer`-based serialization) all require a custom serializer be plugged in.</span></span> <span data-ttu-id="80170-234">A tale scopo, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="80170-234">To do this, perform the following steps:</span></span>  
  
1. <span data-ttu-id="80170-235">Scrivere il comportamento personalizzato derivante dal comportamento <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="80170-235">Write your own behavior deriving from the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.</span></span>  
  
2. <span data-ttu-id="80170-236">Eseguire l'override dei due metodi `CreateSerializer` in modo che restituiscano il serializzatore personalizzato, sia esso <xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer> con il parametro `preserveObjectReferences` impostato su `true` oppure il serializzatore personalizzato <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="80170-236">Override the two `CreateSerializer` methods to return your own serializer (either the <xref:System.Runtime.Serialization.NetDataContractSerializer>, the <xref:System.Runtime.Serialization.DataContractSerializer> with `preserveObjectReferences` set to `true`, or your own custom <xref:System.Runtime.Serialization.XmlObjectSerializer>).</span></span>  
  
3. <span data-ttu-id="80170-237">Prima di aprire l'host del servizio o creare un canale client, rimuovere il comportamento <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> esistente e attivare la classe derivata personalizzata creata nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="80170-237">Before opening the service host or creating a client channel, remove the existing <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> behavior and plug in the custom derived class that you created in the previous steps.</span></span>  
  
 <span data-ttu-id="80170-238">Per ulteriori informazioni sui concetti di serializzazione avanzata, vedere [Serializzazione e deserializzazione](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="80170-238">For more information about advanced serialization concepts, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80170-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80170-239">See also</span></span>

- [<span data-ttu-id="80170-240">Utilizzo della classe XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="80170-240">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)
- [<span data-ttu-id="80170-241">Procedura: attivare il flusso</span><span class="sxs-lookup"><span data-stu-id="80170-241">How to: Enable Streaming</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
- [<span data-ttu-id="80170-242">Procedura: creare un contratto dati di base per una classe o una struttura</span><span class="sxs-lookup"><span data-stu-id="80170-242">How to: Create a Basic Data Contract for a Class or Structure</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
