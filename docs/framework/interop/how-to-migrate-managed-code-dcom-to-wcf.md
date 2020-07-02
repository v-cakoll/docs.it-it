---
title: 'Procedura: Eseguire la migrazione di codice gestito da DCOM a WCF'
description: Eseguire la migrazione delle chiamate al codice gestito DCOM (Distributed Component Object Model) tra i server e i client Windows Communication Foundation (WCF).
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: cc6ac1dd01e17bb184d1f1faca372134d6130d33
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619091"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a><span data-ttu-id="2b7fb-103">Procedura: Eseguire la migrazione di codice gestito da DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="2b7fb-103">How to: Migrate Managed-Code DCOM to WCF</span></span>
<span data-ttu-id="2b7fb-104">Windows Communication Foundation (WCF) è la scelta migliore e più sicura su Distributed Component Object Model (DCOM) per le chiamate di codice gestito tra i server e i client in un ambiente distribuito.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-104">Windows Communication Foundation (WCF) is the recommended and secure choice over Distributed Component Object Model (DCOM) for managed code calls between servers and clients in a distributed environment.</span></span> <span data-ttu-id="2b7fb-105">Questo articolo mostra come eseguire la migrazione del codice da DCOM a WCF per gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-105">This article shows how you to migrate code from DCOM to WCF for the following scenarios.</span></span>  
  
- <span data-ttu-id="2b7fb-106">Il servizio remoto restituisce al client un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="2b7fb-106">The remote service returns an object by-value to the client</span></span>  
  
- <span data-ttu-id="2b7fb-107">Il client invia al servizio remoto un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="2b7fb-107">The client sends an object by-value to the remote service</span></span>  
  
- <span data-ttu-id="2b7fb-108">Il servizio remoto restituisce al client un oggetto in base al riferimento</span><span class="sxs-lookup"><span data-stu-id="2b7fb-108">The remote service returns an object by-reference to the client</span></span>  
  
 <span data-ttu-id="2b7fb-109">Per motivi di sicurezza, l'invio di un oggetto in base al riferimento dal client al servizio non è consentito in WCF.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-109">For security reasons, sending an object by-reference from the client to the service is not allowed in WCF.</span></span> <span data-ttu-id="2b7fb-110">Uno scenario che richiede una conversazione tra il client e il server può essere realizzato in WCF usando un servizio duplex.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-110">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span>  <span data-ttu-id="2b7fb-111">Per altre informazioni sui servizi duplex, vedere [Servizi duplex](../wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-111">For more information about duplex services, see [Duplex Services](../wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="2b7fb-112">Per altri dettagli sulla creazione di servizi e client WCF per tali servizi, vedere [Programmazione WCF di base](../wcf/basic-wcf-programming.md), [Progettazione e implementazione di servizi](../wcf/designing-and-implementing-services.md) e [Creazione di client](../wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-112">For more details about creating WCF services and clients for those services, see [Basic WCF Programming](../wcf/basic-wcf-programming.md), [Designing and Implementing Services](../wcf/designing-and-implementing-services.md), and [Building Clients](../wcf/building-clients.md).</span></span>  
  
## <a name="dcom-example-code"></a><span data-ttu-id="2b7fb-113">Codice di esempio DCOM</span><span class="sxs-lookup"><span data-stu-id="2b7fb-113">DCOM example code</span></span>  
 <span data-ttu-id="2b7fb-114">Per questi scenari, le interfacce DCOM illustrate che usano WCF hanno la seguente struttura:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-114">For these scenarios, the DCOM interfaces that are illustrated using WCF have the following structure:</span></span>  
  
```csharp  
[ComVisible(true)]  
[Guid("AA9C4CDB-55EA-4413-90D2-843F1A49E6E6")]  
public interface IRemoteService  
{  
   Customer GetObjectByValue();  
   IRemoteObject GetObjectByReference();  
   void SendObjectByValue(Customer customer);  
}  
  
[ComVisible(true)]  
[Guid("A12C98DE-B6A1-463D-8C24-81E4BBC4351B")]  
public interface IRemoteObject  
{  
}  
  
public class Customer  
{  
}  
```  
  
## <a name="the-service-returns-an-object-by-value"></a><span data-ttu-id="2b7fb-115">Il servizio restituisce un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="2b7fb-115">The service returns an object by-value</span></span>  
 <span data-ttu-id="2b7fb-116">Per questo scenario, si effettua una chiamata a un servizio e il metodo restituisce un oggetto, che viene passato in base al valore dal server al client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-116">For this scenario, you make a call to a service and it method returns an object, which is passed by-value from the server to the client.</span></span> <span data-ttu-id="2b7fb-117">Questo scenario rappresenta la chiamata COM seguente:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-117">This scenario represents the following COM call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 <span data-ttu-id="2b7fb-118">In questo scenario, il client riceve una copia deserializzata di un oggetto dal servizio remoto.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-118">In this scenario, the client receives a deserialized copy of an object from the remote service.</span></span> <span data-ttu-id="2b7fb-119">Il client può interagire con questa copia locale senza chiamare nuovamente il servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-119">The client can interact with this local copy without calling back to the service.</span></span>  <span data-ttu-id="2b7fb-120">In altre parole, al client viene garantito che il servizio non verrà coinvolto in alcun modo quando verranno chiamati metodi sulla copia locale.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-120">In other words, the client is guaranteed the service will not be involved in any way when methods on the local copy are called.</span></span> <span data-ttu-id="2b7fb-121">Poiché WCF restituisce sempre gli oggetti dal servizio in base al valore, la procedura seguente descrive come creare un normale servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-121">WCF always returns objects from the service by value, so the following steps describe creating a regular WCF service.</span></span>  
  
### <a name="step-1-define-the-wcf-service-interface"></a><span data-ttu-id="2b7fb-122">Passaggio 1: Definire l'interfaccia del servizio WCF</span><span class="sxs-lookup"><span data-stu-id="2b7fb-122">Step 1: Define the WCF service interface</span></span>  
 <span data-ttu-id="2b7fb-123">Definire un'interfaccia pubblica per il servizio WCF e contrassegnarla con l'attributo [<xref:System.ServiceModel.ServiceContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="2b7fb-123">Define a public interface for the WCF service and mark it with the [<xref:System.ServiceModel.ServiceContractAttribute>] attribute.</span></span>  <span data-ttu-id="2b7fb-124">Contrassegnare i metodi che si desidera esporre ai client con l'attributo [<xref:System.ServiceModel.OperationContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="2b7fb-124">Mark the methods you want to expose to clients with the [<xref:System.ServiceModel.OperationContractAttribute>] attribute.</span></span> <span data-ttu-id="2b7fb-125">L'esempio seguente mostra l'uso di questi attributi per identificare l'interfaccia lato server e i metodi dell'interfaccia che possono essere chiamati da un client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-125">The following example shows using these attributes to identify the server-side interface and interface methods a client can call.</span></span> <span data-ttu-id="2b7fb-126">Il metodo usato per questo scenario viene visualizzato in grassetto.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-126">The method used for this scenario is shown in bold.</span></span>  
  
```csharp  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Web;
. . .  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]  
    void StoreCustomer(Customer customer);  
  
    [OperationContract]     Customer GetCustomer(string firstName, string lastName);
  
}  
```  
  
### <a name="step-2-define-the-data-contract"></a><span data-ttu-id="2b7fb-127">Passaggio 2: Definire il contratto dati</span><span class="sxs-lookup"><span data-stu-id="2b7fb-127">Step 2: Define the data contract</span></span>  
 <span data-ttu-id="2b7fb-128">Successivamente, creare un contratto dati per il servizio, che descriverà come verranno scambiati i dati tra il servizio e i client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-128">Next you should create a data contract for the service, which will describe how the data will be exchanged between the service and its clients.</span></span>  <span data-ttu-id="2b7fb-129">Le classi descritte nel contratto dati devono essere contrassegnate con l'attributo [<xref:System.Runtime.Serialization.DataContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="2b7fb-129">Classes described in the data contract should be marked with the [<xref:System.Runtime.Serialization.DataContractAttribute>] attribute.</span></span> <span data-ttu-id="2b7fb-130">Le singole proprietà o i singoli campi che si vuole siano visibili sia per il client che per il server devono essere contrassegnati con l'attributo [<xref:System.Runtime.Serialization.DataMemberAttribute>].</span><span class="sxs-lookup"><span data-stu-id="2b7fb-130">The individual properties or fields you want visible to both client and server should be marked with the [<xref:System.Runtime.Serialization.DataMemberAttribute>] attribute.</span></span> <span data-ttu-id="2b7fb-131">Se si vuole consentire i tipi derivati da una classe nel contratto di dati, è necessario identificarli con l'attributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>].</span><span class="sxs-lookup"><span data-stu-id="2b7fb-131">If you want types derived from a class in the data contract to be allowed, you must identify them with the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute.</span></span> <span data-ttu-id="2b7fb-132">WCF serializzerà o deserializzerà solo i tipi nell'interfaccia del servizio e i tipi identificati come tipi noti.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-132">WCF will only serialize or deserialize types in the service interface and types identified as known types.</span></span> <span data-ttu-id="2b7fb-133">Se si tenta di usare un tipo diverso da un tipo noto, si verificherà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-133">If you attempt to use a type that is not a known type, an exception will occur.</span></span>  
  
 <span data-ttu-id="2b7fb-134">Per altre informazioni sui contratti di dati, vedere [Contratti di dati](../wcf/samples/data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-134">For more information about data contracts, see [Data Contracts](../wcf/samples/data-contracts.md).</span></span>  
  
```csharp  
[DataContract]  
[KnownType(typeof(PremiumCustomer))]  
public class Customer  
{  
    [DataMember]  
    public string Firstname;  
    [DataMember]  
    public string Lastname;  
    [DataMember]  
    public Address DefaultDeliveryAddress;  
    [DataMember]  
    public Address DefaultBillingAddress;  
}  
 [DataContract]  
public class PremiumCustomer : Customer  
{  
    [DataMember]  
    public int AccountID;  
}  
  
 [DataContract]  
public class Address  
{  
    [DataMember]  
    public string Street;  
    [DataMember]  
    public string Zipcode;  
    [DataMember]  
    public string City;  
    [DataMember]  
    public string State;  
    [DataMember]  
    public string Country;  
}  
```  
  
### <a name="step-3-implement-the-wcf-service"></a><span data-ttu-id="2b7fb-135">Passaggio 3: Implementare il servizio WCF</span><span class="sxs-lookup"><span data-stu-id="2b7fb-135">Step 3: Implement the WCF service</span></span>  
 <span data-ttu-id="2b7fb-136">Successivamente, implementare la classe del servizio WCF, che implementa l'interfaccia definita nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-136">Next, you should implement the WCF service class that implements the interface you defined in the previous step.</span></span>  
  
```csharp  
public class CustomerService: ICustomerManager
{  
    public void StoreCustomer(Customer customer)  
    {  
        // write to a database  
    }  
    public Customer GetCustomer(string firstName, string lastName)  
    {  
        // read from a database  
    }  
}  
```  
  
### <a name="step-4-configure-the-service-and-the-client"></a><span data-ttu-id="2b7fb-137">Passaggio 4: Configurare il servizio e il client</span><span class="sxs-lookup"><span data-stu-id="2b7fb-137">Step 4: Configure the service and the client</span></span>  
 <span data-ttu-id="2b7fb-138">Per eseguire un servizio WCF, è necessario dichiarare un endpoint che esponga tale interfaccia del servizio in un URL specifico tramite un'associazione WCF specifica.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-138">To run a WCF service, you need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="2b7fb-139">Un'associazione specifica i dettagli di trasporto, codifica e protocollo che permettono ai client e al server di comunicare.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-139">A binding specifies the transport, encoding and protocol details for the clients and server to communicate.</span></span> <span data-ttu-id="2b7fb-140">In genere i binding si aggiungono ai file di configurazione del progetto del servizio (web.config).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-140">You typically add bindings to the service project’s configuration file (web.config).</span></span> <span data-ttu-id="2b7fb-141">Di seguito viene illustrata una voce di associazione per il servizio di esempio:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-141">The following shows a binding entry for the example service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Server.CustomerService">  
        <endpoint address="http://localhost:8083/CustomerManager"
                  binding="basicHttpBinding"  
                  contract="Shared.ICustomerManager" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2b7fb-142">Successivamente, configurare il client in base alle informazioni di binding specificate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-142">Next, you need to configure the client to match the binding information specified by the service.</span></span> <span data-ttu-id="2b7fb-143">A tale scopo, aggiungere quanto segue al file di configurazione dell'applicazione (app.config) del client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-143">To do so, add the following to the client’s application configuration (app.config) file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="customermanager"
                address="http://localhost:8083/CustomerManager"
                binding="basicHttpBinding"
                contract="Shared.ICustomerManager"/>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="step-5-run-the-service"></a><span data-ttu-id="2b7fb-144">Passaggio 5: Eseguire il servizio</span><span class="sxs-lookup"><span data-stu-id="2b7fb-144">Step 5: Run the service</span></span>  
 <span data-ttu-id="2b7fb-145">Infine, è possibile ospitarlo in modo indipendente in un'applicazione console aggiungendo le righe seguenti all'app di servizio e avviando l'app.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-145">Finally, you can self-host it in a console application by adding the following lines to the service app, and starting the app.</span></span> <span data-ttu-id="2b7fb-146">Per altre informazioni su altri modi per ospitare un'applicazione di servizio WCF, vedere [Servizi host](../wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-146">For more information about other ways to host a WCF service application, [Hosting Services](../wcf/hosting-services.md).</span></span>  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a><span data-ttu-id="2b7fb-147">Passaggio 6: Chiamare il servizio dal client</span><span class="sxs-lookup"><span data-stu-id="2b7fb-147">Step 6: Call the service from the client</span></span>  
 <span data-ttu-id="2b7fb-148">Per chiamare il servizio dal client, è necessario creare una channel factory per il servizio e richiedere un canale che consentirà di chiamare il metodo `GetCustomer` direttamente dal client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-148">To call the service from the client, you need to create a channel factory for the service, and request a channel, which will enable you to directly call the `GetCustomer` method directly from the client.</span></span> <span data-ttu-id="2b7fb-149">Il canale implementa l'interfaccia del servizio e gestisce automaticamente la logica di richiesta/risposta sottostante.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-149">The channel implements the service’s interface and handles the underlying request/reply logic for you.</span></span>  <span data-ttu-id="2b7fb-150">Il valore restituito dalla chiamata del metodo è la copia deserializzata della risposta del servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-150">The return value from that method call is the deserialized copy of the service response.</span></span>  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a><span data-ttu-id="2b7fb-151">Il client invia al server un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="2b7fb-151">The client sends a by-value object to the server</span></span>  
 <span data-ttu-id="2b7fb-152">In questo scenario, il client invia un oggetto al server, in base al valore,</span><span class="sxs-lookup"><span data-stu-id="2b7fb-152">In this scenario, the client sends an object to the server, by-value.</span></span> <span data-ttu-id="2b7fb-153">vale a dire che il server riceverà una copia deserializzata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-153">This means that the server will receive a deserialized copy of the object.</span></span>  <span data-ttu-id="2b7fb-154">Il server può chiamare i metodi su tale copia con la garanzia che non venga eseguito alcun callback nel codice client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-154">The server can call methods on that copy and be guaranteed there is no callback into client code.</span></span> <span data-ttu-id="2b7fb-155">Come accennato in precedenza, i normali scambi di dati in WCF sono in base al valore.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-155">As mentioned previously, normal WCF exchanges of data are by-value.</span></span>  <span data-ttu-id="2b7fb-156">Ciò garantisce che la chiamata di metodi su uno di questi oggetti venga eseguita solo in locale: non verrà richiamato codice sul client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-156">This guarantees that calling methods on one of these objects executes locally only – it will not invoke code on the client.</span></span>  
  
 <span data-ttu-id="2b7fb-157">Questo scenario rappresenta la chiamata al metodo COM seguente:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-157">This scenario represents the following COM method call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 <span data-ttu-id="2b7fb-158">Questo scenario usa lo stesso contratto dati e la stessa interfaccia di servizio del primo esempio.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-158">This scenario uses the same service interface and data contract as shown in the first example.</span></span> <span data-ttu-id="2b7fb-159">Anche i client e il servizio verranno configurati nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-159">In addition, the client and service will be configured in the same way.</span></span> <span data-ttu-id="2b7fb-160">In questo esempio, viene creato un canale per inviare l'oggetto ed eseguirlo nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-160">In this example, a channel is created to send the object and run the same way.</span></span> <span data-ttu-id="2b7fb-161">Per questo esempio, tuttavia, si creerà un client che chiama il servizio, passando un oggetto in base al valore.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-161">However, for this example, you will create a client that calls the service, passing an object by-value.</span></span> <span data-ttu-id="2b7fb-162">Il metodo di servizio che verrà chiamato dal client nel contratto di servizio viene visualizzato in grassetto:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-162">The service method the client will call in the service contract is shown in bold:</span></span>  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a><span data-ttu-id="2b7fb-163">Aggiungere il codice al client che invia un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="2b7fb-163">Add code to the client that sends a by-value object</span></span>  
 <span data-ttu-id="2b7fb-164">Il codice seguente mostra come il client crea un nuovo oggetto Customer in base al valore, crea un canale per comunicare con il servizio `ICustomerManager` e gli invia l'oggetto Customer.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-164">The following code shows how the client creates a new by-value customer object, creates a channel to communicate with the `ICustomerManager` service, and sends the customer object to it.</span></span>  
  
 <span data-ttu-id="2b7fb-165">L'oggetto Customer verrà serializzato e inviato al servizio, dove sarà deserializzato dal servizio in una nuova copia di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-165">The customer object will be serialized, and sent to the service, where it is deserialized by the service into a new copy of that object.</span></span>  <span data-ttu-id="2b7fb-166">Qualsiasi metodo chiamato dal servizio su questo oggetto verrà eseguito solo in locale nel server.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-166">Any methods the service calls on this object will execute only locally on the server.</span></span> <span data-ttu-id="2b7fb-167">È importante notare che questo codice illustra l'invio di un tipo derivato (`PremiumCustomer`).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-167">It’s important to note that this code illustrates sending a derived type (`PremiumCustomer`).</span></span>  <span data-ttu-id="2b7fb-168">Per il contratto di servizio è previsto un oggetto `Customer`, ma il contratto dati di servizio usa l'attributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>] per indicare che è consentito anche `PremiumCustomer`.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-168">The service contract expects a `Customer` object, but the service data contract uses the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute to indicate that `PremiumCustomer` is also allowed.</span></span>  <span data-ttu-id="2b7fb-169">In WCF i tentativi di serializzare o deserializzare qualsiasi altro tipo tramite questa interfaccia di servizio avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-169">WCF will fail attempts to serialize or deserialize any other type via this service interface.</span></span>  
  
```csharp  
PremiumCustomer customer = new PremiumCustomer();  
customer.Firstname = "John";  
customer.Lastname = "Doe";  
customer.DefaultBillingAddress = new Address();  
customer.DefaultBillingAddress.Street = "One Microsoft Way";  
customer.DefaultDeliveryAddress = customer.DefaultBillingAddress;  
customer.AccountID = 42;  
  
ChannelFactory<ICustomerManager> factory =  
   new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager customerManager = factory.CreateChannel();  
customerManager.StoreCustomer(customer);  
```  
  
## <a name="the-service-returns-an-object-by-reference"></a><span data-ttu-id="2b7fb-170">Il servizio restituisce un oggetto in base al riferimento</span><span class="sxs-lookup"><span data-stu-id="2b7fb-170">The service returns an object by reference</span></span>  
 <span data-ttu-id="2b7fb-171">Per questo scenario, l'app client effettua una chiamata al servizio remoto e il metodo restituisce un oggetto, che viene passato in base al riferimento dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-171">For this scenario, the client app makes a call to the remote service and the method returns an object, which is passed by reference from the service to the client.</span></span>  
  
 <span data-ttu-id="2b7fb-172">Come accennato in precedenza, i servizi WCF restituiscono sempre un oggetto in base al valore.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-172">As mentioned previously, WCF services always return object by value.</span></span>  <span data-ttu-id="2b7fb-173">Tuttavia, è possibile ottenere un risultato simile usando la classe <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-173">However, you can achieve a similar result by using the <xref:System.ServiceModel.EndpointAddress10> class.</span></span>  <span data-ttu-id="2b7fb-174"><xref:System.ServiceModel.EndpointAddress10> è un oggetto serializzabile in base al valore che può essere usato dal client per ottenere un oggetto in base al riferimento con sessione sul server.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-174">The <xref:System.ServiceModel.EndpointAddress10> is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span>  
  
 <span data-ttu-id="2b7fb-175">Il comportamento dell'oggetto in base al riferimento in WCF illustrato in questo scenario è diverso da quello in DCOM.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-175">The behavior of the by-reference object in WCF shown in this scenario is different than DCOM.</span></span>  <span data-ttu-id="2b7fb-176">In DCOM, il server può restituire direttamente al client un oggetto in base al riferimento e il client può chiamare i metodi dell'oggetto, che vengono eseguiti nel server.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-176">In DCOM, the server can return a by-reference object to the client directly, and the client can call that object’s methods, which execute on the server.</span></span>  <span data-ttu-id="2b7fb-177">In WCF, tuttavia, l'oggetto restituito è sempre in base al valore.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-177">In WCF, however, the object returned is always by-value.</span></span>  <span data-ttu-id="2b7fb-178">Il client deve accettare tale oggetto in base al valore, rappresentato da <xref:System.ServiceModel.EndpointAddress10>, e usarlo per creare il proprio oggetto in base al riferimento con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-178">The client must take that by-value object, represented by <xref:System.ServiceModel.EndpointAddress10> and use it to create its own sessionful by-reference object.</span></span>  <span data-ttu-id="2b7fb-179">Le chiamate al metodo client sull'oggetto con sessione vengono eseguite sul server. In altre parole, questo oggetto in base al riferimento in WCF è un normale servizio WCF configurato con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-179">The client method calls on the sessionful object execute on the server.In other words, this by-reference object in WCF is a normal WCF service that is configured to be sessionful.</span></span>  
  
 <span data-ttu-id="2b7fb-180">In WCF una sessione è un modo per correlare più messaggi inviati tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-180">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span>  <span data-ttu-id="2b7fb-181">Ciò significa che, una volta che un client ottiene una connessione al servizio, verrà stabilita una sessione tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-181">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span>  <span data-ttu-id="2b7fb-182">Il client userà una singola istanza univoca dell'oggetto sul lato server per tutte le proprie interazioni all'interno di questa singola sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-182">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span> <span data-ttu-id="2b7fb-183">I contratti WCF con sessione sono simili ai modelli di richiesta/risposta di rete orientati alla connessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-183">Sessionful WCF contracts are similar to connection-oriented network request/response patterns.</span></span>  
  
 <span data-ttu-id="2b7fb-184">Questo scenario è rappresentato dal metodo DCOM seguente.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-184">This scenario is represented by the following DCOM method.</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a><span data-ttu-id="2b7fb-185">Passaggio 1: Definire l'interfaccia e l'implementazione del servizio WCF con sessione</span><span class="sxs-lookup"><span data-stu-id="2b7fb-185">Step 1: Define the Sessionful WCF service interface and implementation</span></span>  
 <span data-ttu-id="2b7fb-186">Innanzitutto definire un'interfaccia del servizio WCF contenente l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-186">First, define a WCF service interface that contains the sessionful object.</span></span>  
  
 <span data-ttu-id="2b7fb-187">In questo codice, l'oggetto con sessione è contrassegnato con l'attributo `ServiceContract`, che lo identifica come normale interfaccia del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-187">In this code, the sessionful object is marked with the `ServiceContract` attribute, which identifies it as a regular WCF service interface.</span></span>  <span data-ttu-id="2b7fb-188">Inoltre, la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> viene impostata in modo da indicare che sarà un servizio con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-188">In addition, the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> property is set to indicate it will be a sessionful service.</span></span>  
  
```csharp  
[ServiceContract(SessionMode = SessionMode.Allowed)]  
public interface ISessionBoundObject  
{  
    [OperationContract]  
    string GetCurrentValue();  
  
    [OperationContract]  
    void SetCurrentValue(string value);  
}  
```  
  
 <span data-ttu-id="2b7fb-189">Nel codice seguente viene illustrata l'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-189">The following code shows the service implementation.</span></span>  
  
 <span data-ttu-id="2b7fb-190">Il servizio viene contrassegnato con l'attributo [ServiceBehavior] e la proprietà InstanceContextMode viene impostata su InstanceContextMode.PerSessions per indicare che per ogni sessione deve essere creata un'istanza univoca di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-190">The service is marked with the [ServiceBehavior] attribute, and its InstanceContextMode property set to InstanceContextMode.PerSessions to indicate that a unique instance of this type should be created for each session.</span></span>  
  
```csharp  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
    public class MySessionBoundObject : ISessionBoundObject  
    {  
        private string _value;  
  
        public string GetCurrentValue()  
        {  
            return _value;  
        }  
  
        public void SetCurrentValue(string val)  
        {  
            _value = val;  
        }  
  
    }  
```  
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a><span data-ttu-id="2b7fb-191">Passaggio 2: Definire il servizio factory WCF per l'oggetto con sessione</span><span class="sxs-lookup"><span data-stu-id="2b7fb-191">Step 2: Define the WCF factory service for the sessionful object</span></span>  
 <span data-ttu-id="2b7fb-192">Il servizio che crea l'oggetto con sessione deve essere definito e implementato.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-192">The service that creates the sessionful object must be defined and implemented.</span></span> <span data-ttu-id="2b7fb-193">A tal fine, osservare il codice indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-193">The following code shows how to do this.</span></span> <span data-ttu-id="2b7fb-194">Questo codice crea un altro servizio WCF che restituisce un oggetto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-194">This code creates another WCF service that returns an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  <span data-ttu-id="2b7fb-195">Si tratta di una forma serializzabile di endpoint che può essere usata per creare l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-195">This is a serializable form of an endpoint the can use to create the session-full object.</span></span>  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 <span data-ttu-id="2b7fb-196">Di seguito è riportata l'implementazione di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-196">The following is the implementation of this service.</span></span> <span data-ttu-id="2b7fb-197">Questa implementazione mantiene una channel factory singleton per creare oggetti con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-197">This implementation maintains a singleton channel factory to create sessionful objects.</span></span>  <span data-ttu-id="2b7fb-198">Quando viene chiamato `GetInstanceAddress`, questo crea un canale e un oggetto <xref:System.ServiceModel.EndpointAddress10> che fa riferimento all'indirizzo remoto associato a questo canale.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-198">When `GetInstanceAddress` is called, it creates a channel and creates an <xref:System.ServiceModel.EndpointAddress10> object that points to the remote address associated with this channel.</span></span>   <span data-ttu-id="2b7fb-199"><xref:System.ServiceModel.EndpointAddress10> è un tipo di dati che può essere restituito al client in base al valore.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-199"><xref:System.ServiceModel.EndpointAddress10> is a data type that can be returned to the client by-value.</span></span>
  
```csharp  
public class SessionBoundFactory : ISessionBoundFactory  
    {  
        public static ChannelFactory<ISessionBoundObject> _factory =
            new ChannelFactory<ISessionBoundObject>("sessionbound");  
  
        public SessionBoundFactory()  
        {  
        }  
  
        public EndpointAddress10 GetInstanceAddress()  
        {  
            IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
            return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
        }  
    }  
```  
  
### <a name="step-3-configure-and-start-the-wcf-services"></a><span data-ttu-id="2b7fb-200">Passaggio 3: Configurare e avviare i servizi WCF</span><span class="sxs-lookup"><span data-stu-id="2b7fb-200">Step 3: Configure and start the WCF services</span></span>  
 <span data-ttu-id="2b7fb-201">Per ospitare questi servizi, sarà necessario aggiungere quanto segue al file di configurazione del server (Web.config).</span><span class="sxs-lookup"><span data-stu-id="2b7fb-201">To host these services, you will need to make the following additions to the server’s configuration file (web.config).</span></span>  
  
1. <span data-ttu-id="2b7fb-202">Aggiungere una sezione `<client>` che descrive l'endpoint per l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-202">Add a `<client>` section that describes the endpoint for the sessionful object.</span></span>  <span data-ttu-id="2b7fb-203">In questo scenario, il server funge anche da client e deve essere configurato per abilitare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-203">In this scenario, the server also acts as a client and must be configured to enable this.</span></span>  
  
2. <span data-ttu-id="2b7fb-204">Nella sezione `<services>` dichiarare gli endpoint di servizio per la factory e l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-204">In the `<services>` section, declare service endpoints for the factory and sessionful object.</span></span>  <span data-ttu-id="2b7fb-205">Ciò consente al client di comunicare con gli endpoint di servizio, di acquisire <xref:System.ServiceModel.EndpointAddress10> e di creare il canale con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-205">This enables the client to communicate with the service endpoints, acquire the <xref:System.ServiceModel.EndpointAddress10> and create the sessionful channel.</span></span>  
  
 <span data-ttu-id="2b7fb-206">Di seguito è riportato un esempio di file di configurazione con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-206">The following is an example configuration file with these settings:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="sessionbound"  
                address="net.tcp://localhost:8081/SessionBoundObject"  
                binding="netTcpBinding"  
                contract="Shared.ISessionBoundObject"/>  
    </client>  
  
    <services>  
      <service name="Server.MySessionBoundObject">  
        <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                  binding="netTcpBinding"
                  contract="Shared.ISessionBoundObject" />  
      </service>  
      <service name="Server.SessionBoundFactory">  
        <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                  binding="netTcpBinding"
                  contract="Shared.ISessionBoundFactory" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2b7fb-207">Aggiungere le seguenti righe a un'applicazione console, per ospitare il servizio in modo indipendente, e avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-207">Add the following lines to a console application, to self-host the service, and start the app.</span></span>  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a><span data-ttu-id="2b7fb-208">Passaggio 4: Configurare il client e chiamare il servizio</span><span class="sxs-lookup"><span data-stu-id="2b7fb-208">Step 4: Configure the client and call the service</span></span>  
 <span data-ttu-id="2b7fb-209">Configurare il client per comunicare con i servizi WCF, creando le seguenti voci nel file di configurazione dell'applicazione (app.config) del progetto.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-209">Configure the client to communicate with the WCF services by making the following entries in the project’s application configuration file (app.config).</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="sessionbound"
                address="net.tcp://localhost:8081/SessionBoundObject"
                binding="netTcpBinding"
                contract="Shared.ISessionBoundObject"/>  
      <endpoint name="factory"
                address="net.tcp://localhost:8081/SessionBoundFactory"
                binding="netTcpBinding"
                contract="Shared.ISessionBoundFactory"/>  
    </client>
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2b7fb-210">Per chiamare il servizio, aggiungere il codice al client per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b7fb-210">To call the service, add the code to the client to do the following:</span></span>  
  
1. <span data-ttu-id="2b7fb-211">Creare un canale per il servizio `ISessionBoundFactory`.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-211">Create a channel to the `ISessionBoundFactory` service.</span></span>  
  
2. <span data-ttu-id="2b7fb-212">Usare il canale per richiamare il servizio `ISessionBoundFactory` e ottenere un oggetto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-212">Use the channel to invoke the `ISessionBoundFactory` service an obtain an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  
  
3. <span data-ttu-id="2b7fb-213">Usare <xref:System.ServiceModel.EndpointAddress10> per creare un canale in modo da ottenere un oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-213">Use the <xref:System.ServiceModel.EndpointAddress10> to create a channel to obtain a sessionful object.</span></span>  
  
4. <span data-ttu-id="2b7fb-214">Chiamare i metodi `SetCurrentValue` e `GetCurrentValue` per dimostrare che l'istanza dell'oggetto usata in più chiamate è sempre la stessa.</span><span class="sxs-lookup"><span data-stu-id="2b7fb-214">Call the `SetCurrentValue` and `GetCurrentValue` methods to demonstrate it remains the same object instance is used across multiple calls.</span></span>  
  
```csharp  
ChannelFactory<ISessionBoundFactory> factory =  
        new ChannelFactory<ISessionBoundFactory>("factory");  
  
ISessionBoundFactory sessionBoundFactory = factory.CreateChannel();  
  
EndpointAddress10 address = sessionBoundFactory.GetInstanceAddress();  
  
ChannelFactory<ISessionBoundObject> sessionBoundObjectFactory =  
    new ChannelFactory<ISessionBoundObject>(  
        new NetTcpBinding(),  
        address.ToEndpointAddress());  
  
ISessionBoundObject sessionBoundObject =  
        sessionBoundObjectFactory.CreateChannel();  
  
sessionBoundObject.SetCurrentValue("Hello");  
if (sessionBoundObject.GetCurrentValue() == "Hello")  
{  
    Console.WriteLine("Session-full instance management works as expected");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b7fb-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b7fb-215">See also</span></span>

- [<span data-ttu-id="2b7fb-216">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="2b7fb-216">Basic WCF Programming</span></span>](../wcf/basic-wcf-programming.md)
- [<span data-ttu-id="2b7fb-217">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="2b7fb-217">Designing and Implementing Services</span></span>](../wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="2b7fb-218">Creazione di client</span><span class="sxs-lookup"><span data-stu-id="2b7fb-218">Building Clients</span></span>](../wcf/building-clients.md)
- [<span data-ttu-id="2b7fb-219">Servizi duplex</span><span class="sxs-lookup"><span data-stu-id="2b7fb-219">Duplex Services</span></span>](../wcf/feature-details/duplex-services.md)
