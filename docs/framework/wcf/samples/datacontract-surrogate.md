---
title: Surrogato di DataContract
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: 7ef78c4361c055d7be35c03a3c8717e86aceddab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183827"
---
# <a name="datacontract-surrogate"></a><span data-ttu-id="3f3df-102">Surrogato di DataContract</span><span class="sxs-lookup"><span data-stu-id="3f3df-102">DataContract Surrogate</span></span>
<span data-ttu-id="3f3df-103">In questo esempio viene illustrato come la serializzazione, la deserializzazione, l'esportazione e l'importazione di schemi possano essere personalizzate utilizzando una classe surrogata del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="3f3df-103">This sample demonstrates how processes like serialization, deserialization, schema export, and schema import can be customized using a data contract surrogate class.</span></span> <span data-ttu-id="3f3df-104">In questo esempio viene illustrato come utilizzare un surrogato in uno scenario client e server in cui i dati vengono serializzati e trasmessi tra un servizio e un client Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3f3df-104">This sample shows how to use a surrogate in a client and server scenario where data is serialized and transmitted between a Windows Communication Foundation (WCF) client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f3df-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3f3df-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3f3df-106">Nell'esempio di codice seguente viene utilizzato il contratto di servizio seguente:</span><span class="sxs-lookup"><span data-stu-id="3f3df-106">The sample uses the following service contract:</span></span>  
  
```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 <span data-ttu-id="3f3df-107">L'operazione `AddEmployee` consente agli utenti di aggiungere dati relativi ai nuovi dipendenti e l'operazione `GetEmployee` supporta la ricerca dei dipendenti in base al nome.</span><span class="sxs-lookup"><span data-stu-id="3f3df-107">The `AddEmployee` operation allows users to add data about new employees and the `GetEmployee` operation supports search for employees based on name.</span></span>  
  
 <span data-ttu-id="3f3df-108">Queste operazioni utilizzano il tipo di dati seguente:</span><span class="sxs-lookup"><span data-stu-id="3f3df-108">These operations use the following data type:</span></span>  
  
```csharp
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 <span data-ttu-id="3f3df-109">Nel tipo `Employee`, la classe `Person` (descritta nell'esempio di codice seguente) non può essere serializzata da <xref:System.Runtime.Serialization.DataContractSerializer> perché non è una classe del contratto dati valida.</span><span class="sxs-lookup"><span data-stu-id="3f3df-109">In the `Employee` type, the `Person` class (shown in the following sample code) cannot be serialized by the <xref:System.Runtime.Serialization.DataContractSerializer> because it is not a valid data contract class.</span></span>  
  
```csharp
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 <span data-ttu-id="3f3df-110">È possibile applicare l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> alla classe `Person`, ma questa operazione non è sempre possibile.</span><span class="sxs-lookup"><span data-stu-id="3f3df-110">You can apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the `Person` class, but this is not always possible.</span></span> <span data-ttu-id="3f3df-111">Ad esempio, la classe `Person` può essere definita in un assembly separato sul quale non si ha alcun controllo.</span><span class="sxs-lookup"><span data-stu-id="3f3df-111">For example, the `Person` class can be defined in a separate assembly over which you have no control.</span></span>  
  
 <span data-ttu-id="3f3df-112">Data questa restrizione, un modo di serializzare la classe `Person` è di sostituirla con un'altra classe contrassegnata con <xref:System.Runtime.Serialization.DataContractAttribute> e copiare i dati necessari nella nuova classe.</span><span class="sxs-lookup"><span data-stu-id="3f3df-112">Given this restriction, one way to serialize the `Person` class is to substitute it with another class that is marked with <xref:System.Runtime.Serialization.DataContractAttribute> and copy over necessary data to the new class.</span></span> <span data-ttu-id="3f3df-113">L'obiettivo è che la classe `Person` appaia come una classe DataContract per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3f3df-113">The objective is to make the `Person` class appear as a DataContract to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="3f3df-114">Si noti che questo è un modo di serializzare classi diverse da DataContract.</span><span class="sxs-lookup"><span data-stu-id="3f3df-114">Note that this is one way to serialize non-data contract classes.</span></span>  
  
 <span data-ttu-id="3f3df-115">L'esempio sostituisce logicamente la classe `Person` con una classe diversa denominata `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-115">The sample logically replaces the `Person` class with a different class named `PersonSurrogated`.</span></span>  
  
```csharp
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 <span data-ttu-id="3f3df-116">Per eseguire questa sostituzione, viene utilizzato il surrogato del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="3f3df-116">The data contract surrogate is used to achieve this replacement.</span></span> <span data-ttu-id="3f3df-117">Un surrogato di un contratto dati rappresenta una classe che implementa <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span><span class="sxs-lookup"><span data-stu-id="3f3df-117">A data contract surrogate is a class that implements <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span></span> <span data-ttu-id="3f3df-118">In questo esempio, la classe `AllowNonSerializableTypesSurrogate` implementa questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3f3df-118">In this sample, the `AllowNonSerializableTypesSurrogate` class implements this interface.</span></span>  
  
 <span data-ttu-id="3f3df-119">Nell'implementazione dell'interfaccia, la prima attività consiste nello stabilire un mapping dei tipi da `Person` a `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-119">In the interface implementation, the first task is to establish a type mapping from `Person` to `PersonSurrogated`.</span></span> <span data-ttu-id="3f3df-120">Questo mapping viene utilizzato sia al momento della serializzazione che al momento dell'esportazione degli schemi.</span><span class="sxs-lookup"><span data-stu-id="3f3df-120">This is used both at serialization time as well as at schema export time.</span></span> <span data-ttu-id="3f3df-121">Questo mapping viene realizzato implementando il metodo <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29>.</span><span class="sxs-lookup"><span data-stu-id="3f3df-121">This mapping is achieved by implementing the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> method.</span></span>  
  
```csharp
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 <span data-ttu-id="3f3df-122">Il metodo <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> esegue il mapping di un'istanza `Person` a un'istanza `PersonSurrogated` durante il serializzazione, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3f3df-122">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> method maps a `Person` instance to a `PersonSurrogated` instance during serialization, as shown in the following sample code.</span></span>  
  
```csharp
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="3f3df-123">Il metodo <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> fornisce il mapping inverso per la deserializzazione, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3f3df-123">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> method provides the reverse mapping for deserialization, as shown in the following sample code.</span></span>  
  
```csharp
public object GetDeserializedObject(object obj,
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="3f3df-124">Per eseguire il mapping del contratto dati `PersonSurrogated` alla classe `Person` esistente durante l'importazione degli schemi, l'esempio implementa il metodo <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29>, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3f3df-124">To map the `PersonSurrogated` data contract to the existing `Person` class during schema import, the sample implements the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> method, as shown in the following sample code.</span></span>  
  
```csharp
public Type GetReferencedTypeOnImport(string typeName,
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 <span data-ttu-id="3f3df-125">Nell'esempio di codice seguente viene completata l'implementazione dell'interfaccia <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span><span class="sxs-lookup"><span data-stu-id="3f3df-125">The following sample code completes the implementation of the <xref:System.Runtime.Serialization.IDataContractSurrogate> interface.</span></span>  
  
```csharp
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 <span data-ttu-id="3f3df-126">In questo esempio, il surrogato viene attivato in ServiceModel da un attributo denominato `AllowNonSerializableTypesAttribute`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-126">In this sample, the surrogate is enabled in ServiceModel by an attribute called `AllowNonSerializableTypesAttribute`.</span></span> <span data-ttu-id="3f3df-127">Gli sviluppatori devono applicare questo attributo al contratto di servizio, come illustrato nel contratto di servizio `IPersonnelDataService` precedente.</span><span class="sxs-lookup"><span data-stu-id="3f3df-127">Developers would need to apply this attribute on their service contract as shown on the `IPersonnelDataService` service contract above.</span></span> <span data-ttu-id="3f3df-128">Questo attributo implementa `IContractBehavior` e configura il surrogato sulle operazioni nei metodi `ApplyClientBehavior` e `ApplyDispatchBehavior`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-128">This attribute implements `IContractBehavior` and sets up the surrogate on operations in its `ApplyClientBehavior` and `ApplyDispatchBehavior` methods.</span></span>  
  
 <span data-ttu-id="3f3df-129">In questo caso l'attributo non è necessario: in questo esempio viene utilizzato solo per scopi dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="3f3df-129">The attribute is not necessary in this case - it is used for demonstration purposes in this sample.</span></span> <span data-ttu-id="3f3df-130">In alternativa gli utenti possono attivare un surrogato aggiungendo manualmente `IContractBehavior`, `IEndpointBehavior` o `IOperationBehavior` simili utilizzando il codice o la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3f3df-130">Users can alternatively enable a surrogate by manually adding a similar `IContractBehavior`, `IEndpointBehavior` or `IOperationBehavior` using code or using configuration.</span></span>  
  
 <span data-ttu-id="3f3df-131">L'implementazione `IContractBehavior` cerca le operazioni che utilizzano DataContract verificando se hanno registrato un `DataContractSerializerOperationBehavior`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-131">The `IContractBehavior` implementation looks for operations that use DataContract by checking if they have a `DataContractSerializerOperationBehavior` registered.</span></span> <span data-ttu-id="3f3df-132">In questo caso, imposta la proprietà `DataContractSurrogate` su quel comportamento.</span><span class="sxs-lookup"><span data-stu-id="3f3df-132">If they do, it sets the `DataContractSurrogate` property on that behavior.</span></span> <span data-ttu-id="3f3df-133">Nell'esempio di codice seguente, viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="3f3df-133">The following sample code shows how this is done.</span></span> <span data-ttu-id="3f3df-134">L'impostazione del surrogato su questo comportamento dell'operazione lo abilita per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="3f3df-134">Setting the surrogate on this operation behavior enables it for serialization and deserialization.</span></span>  
  
```csharp
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 <span data-ttu-id="3f3df-135">È necessario eseguire altri passaggi per inserire il surrogato perché possa essere utilizzato durante la generazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="3f3df-135">Additional steps need to be taken to plug in the surrogate for use during metadata generation.</span></span> <span data-ttu-id="3f3df-136">Un modo di eseguire questa operazione è di fornire un `IWsdlExportExtension`, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3f3df-136">One mechanism to do this is to provide an `IWsdlExportExtension` which is what this sample demonstrates.</span></span> <span data-ttu-id="3f3df-137">Un altro modo è di modificare direttamente `WsdlExporter`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-137">Another way is to modify the `WsdlExporter` directly.</span></span>  
  
 <span data-ttu-id="3f3df-138">L'attributo `AllowNonSerializableTypesAttribute` implementa `IWsdlExportExtension` e `IContractBehavior`.</span><span class="sxs-lookup"><span data-stu-id="3f3df-138">The `AllowNonSerializableTypesAttribute` attribute implements `IWsdlExportExtension` and `IContractBehavior`.</span></span> <span data-ttu-id="3f3df-139">L'estensione può `IContractBehavior` essere `IEndpointBehavior` un o in questo caso.</span><span class="sxs-lookup"><span data-stu-id="3f3df-139">The extension can be either an `IContractBehavior` or `IEndpointBehavior` in this case.</span></span> <span data-ttu-id="3f3df-140">L'implementazione del metodo `IWsdlExportExtension.ExportContract` abilita il surrogato aggiungendolo al `XsdDataContractExporter` utilizzato durante la generazione degli schemi DataContract.</span><span class="sxs-lookup"><span data-stu-id="3f3df-140">Its `IWsdlExportExtension.ExportContract` method implementation enables the surrogate by adding it to the `XsdDataContractExporter` used during schema generation for DataContract.</span></span> <span data-ttu-id="3f3df-141">Nel frammento di codice seguente viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="3f3df-141">The following code snippet shows how to do this.</span></span>  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 <span data-ttu-id="3f3df-142">Quando si esegue l'esempio, il client chiama AddEmployee, quindi chiama GetEmployee per verificare se la prima chiamata è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3f3df-142">When you run the sample, the client calls AddEmployee followed by a GetEmployee call to check if the first call was successful.</span></span> <span data-ttu-id="3f3df-143">Il risultato della richiesta di un'operazione GetEmployee viene visualizzato nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="3f3df-143">The result of the GetEmployee operation request is displayed in the client console window.</span></span> <span data-ttu-id="3f3df-144">L'operazione GetEmployee deve riuscire a trovare il dipendente e stampare "trovato".</span><span class="sxs-lookup"><span data-stu-id="3f3df-144">The GetEmployee operation must succeed in finding the employee and print "found".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f3df-145">In questo esempio viene illustrato come inserire un surrogato per la serializzazione, la deserializzazione e la generazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="3f3df-145">This sample shows how to plug in a surrogate for serialize, deserialize and metadata generation.</span></span> <span data-ttu-id="3f3df-146">Non viene descritto come inserire un surrogato per la generazione di codice dai metadati.</span><span class="sxs-lookup"><span data-stu-id="3f3df-146">It does not show how to plug in a surrogate for code generation from metadata.</span></span> <span data-ttu-id="3f3df-147">Per visualizzare un esempio di come un surrogato può essere utilizzato per inserire la generazione di codice client, vedere l'esempio di [pubblicazione WSDL personalizzata.](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)</span><span class="sxs-lookup"><span data-stu-id="3f3df-147">To see a sample of how a surrogate can be used to plug into client code generation, see the [Custom WSDL Publication](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) sample.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3f3df-148">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3f3df-148">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3f3df-149">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3f3df-149">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3f3df-150">Per compilare l'edizione della soluzione in linguaggio C, seguire le istruzioni in [Compilazione degli](../../../../docs/framework/wcf/samples/building-the-samples.md)esempi di Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="3f3df-150">To build the C# edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="3f3df-151">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3f3df-151">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3f3df-152">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3f3df-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3f3df-153">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3f3df-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3f3df-154">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3f3df-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3f3df-155">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3f3df-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
