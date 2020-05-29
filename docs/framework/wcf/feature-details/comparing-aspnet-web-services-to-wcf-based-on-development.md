---
title: Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: c5a2145a6d7b631a666df94eb0c1fc53cbc3c55f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202270"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="024b7-102">Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo</span><span class="sxs-lookup"><span data-stu-id="024b7-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>

<span data-ttu-id="024b7-103">Windows Communication Foundation (WCF) dispone di un'opzione della modalità di compatibilità ASP.NET per consentire la programmazione e la configurazione delle applicazioni WCF come servizi Web ASP.NET e simulare il comportamento.</span><span class="sxs-lookup"><span data-stu-id="024b7-103">Windows Communication Foundation (WCF) has an ASP.NET compatibility mode option to enable WCF applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="024b7-104">Nelle sezioni seguenti vengono confrontati i servizi Web di ASP.NET e WCF in base a ciò che è necessario per sviluppare applicazioni con entrambe le tecnologie.</span><span class="sxs-lookup"><span data-stu-id="024b7-104">The following sections compare ASP.NET Web services and WCF based on what is required to develop applications using both technologies.</span></span>

## <a name="data-representation"></a><span data-ttu-id="024b7-105">Rappresentazione dei dati</span><span class="sxs-lookup"><span data-stu-id="024b7-105">Data Representation</span></span>

<span data-ttu-id="024b7-106">Lo sviluppo di un servizio Web con ASP.NET inizia in genere con la definizione di qualsiasi tipo di dati complesso che il servizio deve usare.</span><span class="sxs-lookup"><span data-stu-id="024b7-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="024b7-107">ASP.NET si basa sulla classe <xref:System.Xml.Serialization.XmlSerializer> per tradurre dati rappresentati da tipi .NET Framework in dati XML per la trasmissione a o da un servizio, nonché per tradurre dati ricevuti come XML in oggetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="024b7-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="024b7-108">La definizione dei tipi di dati complessi che un servizio ASP.NET deve usare richiede la definizione di classi .NET Framework che la classe <xref:System.Xml.Serialization.XmlSerializer> può serializzare in e da XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="024b7-109">Tali classi possono essere scritte manualmente o generate da definizioni dei tipi in XML Schema usando l'utilità della riga di comando XML Schemas/Data Types Support Utility, xsd.exe.</span><span class="sxs-lookup"><span data-stu-id="024b7-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>

<span data-ttu-id="024b7-110">Di seguito sono elencati i principali aspetti da considerare nella definizione di classi .NET Framework che la classe <xref:System.Xml.Serialization.XmlSerializer> può serializzare in XML e da XML:</span><span class="sxs-lookup"><span data-stu-id="024b7-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>

- <span data-ttu-id="024b7-111">Soltanto i campi e le proprietà pubbliche di oggetti .NET Framework vengono tradotti in XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>

- <span data-ttu-id="024b7-112">Le istanze di classi di raccolte possono essere serializzate in XML soltanto se le classi implementano l'interfaccia <xref:System.Collections.IEnumerable> o <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="024b7-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>

- <span data-ttu-id="024b7-113">Le classi che implementano l'interfaccia <xref:System.Collections.IDictionary>, ad esempio <xref:System.Collections.Hashtable>, non possono essere serializzate in XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>

- <span data-ttu-id="024b7-114">I numerosi tipi di attributo nello spazio dei nomi <xref:System.Xml.Serialization> possono essere aggiunti a una classe .NET Framework e ai relativi membri per controllare in che modo le istanze della classe vengono rappresentate in XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>

<span data-ttu-id="024b7-115">Lo sviluppo di applicazioni WCF inizia in genere anche con la definizione di tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="024b7-115">WCF application development usually also begins with the definition of complex types.</span></span> <span data-ttu-id="024b7-116">È possibile eseguire WCF per utilizzare gli stessi tipi di .NET Framework dei servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-116">WCF can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>

<span data-ttu-id="024b7-117">WCF <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> possono essere aggiunti ai tipi di .NET Framework per indicare che le istanze del tipo devono essere serializzate in XML e quali particolari campi o proprietà del tipo devono essere serializzati, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="024b7-117">The WCF<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>

```csharp
//Example One:
[DataContract]
public class LineItem
{
    [DataMember]
    public string ItemNumber;
    [DataMember]
    public decimal Quantity;
    [DataMember]
    public decimal UnitPrice;
}

//Example Two:
public class LineItem
{
    [DataMember]
    private string itemNumber;
    [DataMember]
    private decimal quantity;
    [DataMember]
    private decimal unitPrice;

    public string ItemNumber
    {
      get
      {
          return this.itemNumber;
      }

      set
      {
          this.itemNumber = value;
      }
    }

    public decimal Quantity
    {
        get
        {
            return this.quantity;
        }

        set
        {
            this.quantity = value;
        }
    }

    public decimal UnitPrice
    {
      get
      {
          return this.unitPrice;
      }

      set
      {
          this.unitPrice = value;
      }
    }
}

//Example Three:
public class LineItem
{
     private string itemNumber;
     private decimal quantity;
     private decimal unitPrice;

     [DataMember]
     public string ItemNumber
     {
       get
       {
          return this.itemNumber;
       }

       set
       {
           this.itemNumber = value;
       }
     }

     [DataMember]
     public decimal Quantity
     {
          get
          {
              return this.quantity;
          }

          set
          {
             this.quantity = value;
          }
     }

     [DataMember]
     public decimal UnitPrice
     {
          get
          {
              return this.unitPrice;
          }

          set
          {
              this.unitPrice = value;
          }
     }
}
```

<span data-ttu-id="024b7-118"><xref:System.Runtime.Serialization.DataContractAttribute> significa che nessuno dei campi o proprietà di un tipo o altri campi o proprietà di un tipo devono essere serializzati, mentre <xref:System.Runtime.Serialization.DataMemberAttribute> indica che un deve essere serializzato un particolare campo o proprietà.</span><span class="sxs-lookup"><span data-stu-id="024b7-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="024b7-119">L'attributo <xref:System.Runtime.Serialization.DataContractAttribute> può essere applicato a una classe o a una struttura.</span><span class="sxs-lookup"><span data-stu-id="024b7-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="024b7-120">L'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> può essere applicato a un campo o a una proprietà e i campi e le proprietà alle quali viene applicato l'attributo possono essere pubbliche o private.</span><span class="sxs-lookup"><span data-stu-id="024b7-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="024b7-121">Le istanze di tipi a cui è <xref:System.Runtime.Serialization.DataContractAttribute> applicato il sono definite contratti dati in WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in WCF.</span></span> <span data-ttu-id="024b7-122">Vengono serializzate in XML usando <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="024b7-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

<span data-ttu-id="024b7-123">Nell'elenco seguente sono descritte le principali differenze tra l'uso di <xref:System.Runtime.Serialization.DataContractSerializer> e l'uso di <xref:System.Xml.Serialization.XmlSerializer> e dei vari attributi dello spazio dei nomi <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="024b7-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>

- <span data-ttu-id="024b7-124">La classe <xref:System.Xml.Serialization.XmlSerializer> e gli attributi dello spazio dei nomi <xref:System.Xml.Serialization> consentono di eseguire il mapping di tipi .NET Framework a qualsiasi tipo valido definito nell'XML Schema e forniscono pertanto un controllo preciso della modalità di rappresentazione di un tipo in XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="024b7-125">Gli attributi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> forniscono invece un controllo limitato sulla modalità di rappresentazione di un tipo in XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="024b7-126">È possibile specificare soltanto gli spazi dei nomi e i nomi usati per rappresentare il tipo e i relativi campi o proprietà in XML e la sequenza nella quale i campi e le proprietà vengono visualizzate in XML:</span><span class="sxs-lookup"><span data-stu-id="024b7-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>

  ```csharp
  [DataContract(
  Namespace="urn:Contoso:2006:January:29",
  Name="LineItem")]
  public class LineItem
  {
        [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]
        public string itemNumber;
        [DataMember(Name="Quantity",IsRequired=false,Order = 1)]
        public decimal quantity;
        [DataMember(Name="Price",IsRequired=false,Order = 2)]
        public decimal unitPrice;
  }
  ```

  <span data-ttu-id="024b7-127">Qualsiasi altro elemento relativo alla struttura dell'XML Schema usato per rappresentare il tipo .NET è determinata da <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="024b7-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

- <span data-ttu-id="024b7-128">Non consentendo un controllo esteso sulla modalità di rappresentazione di un tipo in XML, il processo di serializzazione diventa estremamente prevedibile per <xref:System.Runtime.Serialization.DataContractSerializer>e quindi più facile da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="024b7-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="024b7-129">Un vantaggio pratico della struttura della classe <xref:System.Runtime.Serialization.DataContractSerializer> sono prestazioni più avanzate, approssimativamente del dieci percento.</span><span class="sxs-lookup"><span data-stu-id="024b7-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>

- <span data-ttu-id="024b7-130">Gli attributi da usare con la classe <xref:System.Xml.Serialization.XmlSerializer> non indicano quali campi o proprietà del tipo vengono serializzati in XML, mentre l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> da usare con la classe <xref:System.Runtime.Serialization.DataContractSerializer> mostra esplicitamente quali campi o proprietà vengono serializzati.</span><span class="sxs-lookup"><span data-stu-id="024b7-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="024b7-131">I contratti dati sono quindi contratti espliciti sulla struttura dei dati che un'applicazione deve inviare e ricevere.</span><span class="sxs-lookup"><span data-stu-id="024b7-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>

- <span data-ttu-id="024b7-132">La classe <xref:System.Xml.Serialization.XmlSerializer> può tradurre soltanto i membri pubblici di un oggetto .NET in XML, mentre la classe <xref:System.Runtime.Serialization.DataContractSerializer> può tradurre i membri di oggetti in XML indipendentemente dai modificatori di accesso di tali membri.</span><span class="sxs-lookup"><span data-stu-id="024b7-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>

- <span data-ttu-id="024b7-133">Poiché è in grado di serializzare membri non pubblici di tipi in XML, la classe <xref:System.Runtime.Serialization.DataContractSerializer> ha meno restrizioni sulla varietà dei tipi .NET che può serializzare in XML.</span><span class="sxs-lookup"><span data-stu-id="024b7-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="024b7-134">In particolare, questa classe può tradurre in XML tipi quali <xref:System.Collections.Hashtable> che implementano l'interfaccia <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="024b7-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="024b7-135">Con maggiore probabilità la classe <xref:System.Runtime.Serialization.DataContractSerializer> è in grado di serializzare in XML le istanze di qualsiasi tipo .NET preesistente senza dover modificare la definizione del tipo o sviluppare un wrapper specifico.</span><span class="sxs-lookup"><span data-stu-id="024b7-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>

- <span data-ttu-id="024b7-136">Un'altra conseguenza della capacità della classe <xref:System.Runtime.Serialization.DataContractSerializer> di accedere ai membri non pubblici di un tipo è che richiede attendibilità totale, diversamente dalla classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="024b7-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="024b7-137">L'autorizzazione di accesso al codice con attendibilità totale fornisce l'accesso completo a tutte le risorse in un computer a cui è possibile accedere utilizzando le credenziali utilizzate per l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="024b7-137">The Full Trust code access permission gives complete access to all resources on a machine that can be accessed using the credentials under which the code is executing.</span></span> <span data-ttu-id="024b7-138">Questa opzione deve essere usata con cautela perché il codice completamente attendibile accede a tutte le risorse nel computer.</span><span class="sxs-lookup"><span data-stu-id="024b7-138">This option should be used with care as fully trusted code accesses all resources on your machine.</span></span>

- <span data-ttu-id="024b7-139">La classe <xref:System.Runtime.Serialization.DataContractSerializer> include alcune funzionalità di supporto per il controllo delle versioni:</span><span class="sxs-lookup"><span data-stu-id="024b7-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>

  - <span data-ttu-id="024b7-140"><xref:System.Runtime.Serialization.DataMemberAttribute> ha una proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> alla quale può essere assegnato un valore false per i membri che vengono aggiunti a nuove versioni di un contratto dati che non erano presenti nelle versioni precedenti, consentendo così alle applicazioni con le nuove versioni del contratto di essere in grado di elaborare versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="024b7-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>

  - <span data-ttu-id="024b7-141">Se per un contratto dati viene implementata l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject>, è possibile consentire alla classe <xref:System.Runtime.Serialization.DataContractSerializer> di passare membri definiti in versioni più recenti di un contratto dati mediante applicazioni con versioni precedenti del contratto.</span><span class="sxs-lookup"><span data-stu-id="024b7-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>

<span data-ttu-id="024b7-142">Nonostante tutte le differenze, il codice XML in cui la classe <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo per impostazione predefinita è semanticamente identico al codice XML in cui la classe <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, a condizione che lo spazio dei nomi per il codice XML sia definito esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="024b7-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="024b7-143">La classe seguente, che include attributi da utilizzare con entrambi i serializzatori, viene convertita in XML semanticamente identico da <xref:System.Xml.Serialization.XmlSerializer> e da <xref:System.Runtime.Serialization.DataContractAttribute> :</span><span class="sxs-lookup"><span data-stu-id="024b7-143">The following class, which has attributes for use with both of the serializers, is translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>

```csharp
[Serializable]
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]
[DataContract(Namespace="urn:Contoso:2006:January:29")]
public class LineItem
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}
```

<span data-ttu-id="024b7-144">Windows Software Development Kit (SDK) include uno strumento da riga di comando denominato [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="024b7-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="024b7-145">Analogamente allo strumento XSD. exe utilizzato con i servizi Web di ASP.NET, Svcutil. exe può generare definizioni di tipi di dati .NET da XML Schema.</span><span class="sxs-lookup"><span data-stu-id="024b7-145">Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="024b7-146">I tipi sono contratti dati se la classe <xref:System.Runtime.Serialization.DataContractSerializer> può generare codice XML nel formato definito dall'XML Schema. In caso contrario, sono destinati alla serializzazione mediante l'uso della classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="024b7-146">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="024b7-147">Svcutil. exe può inoltre generare un XML Schema dai contratti dati utilizzando il relativo `dataContractOnly` comcambio.</span><span class="sxs-lookup"><span data-stu-id="024b7-147">Svcutil.exe can also generate an XML schema from data contracts by using its `dataContractOnly` switch.</span></span>

> [!NOTE]
> <span data-ttu-id="024b7-148">Sebbene i servizi Web di ASP.NET usino il <xref:System.Xml.Serialization.XmlSerializer> e la modalità di compatibilità wcf ASP.NET fa in modo che i servizi WCF rispecchino il comportamento dei servizi web ASP.NET, l'opzione di compatibilità ASP.NET non ne limita l'utilizzo <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="024b7-148">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and WCF ASP.NET compatibility mode makes WCF services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="024b7-149">È comunque possibile usare la classe <xref:System.Runtime.Serialization.DataContractSerializer> con servizi che sono in esecuzione nella modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-149">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>

## <a name="service-development"></a><span data-ttu-id="024b7-150">Sviluppo del servizio</span><span class="sxs-lookup"><span data-stu-id="024b7-150">Service Development</span></span>

<span data-ttu-id="024b7-151">Per sviluppare un servizio usando ASP.NET veniva in genere aggiunto l'attributo <xref:System.Web.Services.WebService> a una classe e l'attributo <xref:System.Web.Services.WebMethodAttribute> a uno dei metodi di tale classe che devono essere operazioni del servizio:</span><span class="sxs-lookup"><span data-stu-id="024b7-151">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>

```csharp
[WebService]
public class Service : T:System.Web.Services.WebService
{
    [WebMethod]
    public string Echo(string input)
    {
       return input;
    }
}
```

<span data-ttu-id="024b7-152">ASP.NET 2.0 ha introdotto l'opzione di aggiunta dell'attributo <xref:System.Web.Services.WebService> e di <xref:System.Web.Services.WebMethodAttribute> a un'interfaccia piuttosto che a una classe e di scrittura di una classe per implementare l'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="024b7-152">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>

```csharp
[WebService]
public interface IEcho
{
    [WebMethod]
    string Echo(string input);
}

public class Service : IEcho
{

   public string Echo(string input)
   {
        return input;
    }
}
```

<span data-ttu-id="024b7-153">È preferibile usare questa opzione in quanto l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare lo stesso contratto in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="024b7-153">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>

<span data-ttu-id="024b7-154">Un servizio WCF viene fornito definendo uno o più endpoint WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-154">A WCF service is provided by defining one or more WCF endpoints.</span></span> <span data-ttu-id="024b7-155">Un endpoint è definito da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-155">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="024b7-156">L'indirizzo definisce l'ubicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-156">The address defines where the service is located.</span></span> <span data-ttu-id="024b7-157">L'associazione specifica come comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-157">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="024b7-158">Il contratto di servizio definisce le operazioni che il servizio può eseguire.</span><span class="sxs-lookup"><span data-stu-id="024b7-158">The service contract defines the operations that the service can perform.</span></span>

<span data-ttu-id="024b7-159">Il contratto di servizio viene in genere definito per primo, aggiungendo <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> a un'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="024b7-159">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

<span data-ttu-id="024b7-160"><xref:System.ServiceModel.ServiceContractAttribute>Specifica che l'interfaccia definisce un contratto di servizio WCF e <xref:System.ServiceModel.OperationContractAttribute> indica quale, se presente, i metodi dell'interfaccia definiscono le operazioni del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-160">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a WCF service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>

<span data-ttu-id="024b7-161">Una volta che è stato definito, il contratto di servizio viene implementato in una classe, facendo in modo che la classe implementi l'interfaccia mediante la quale viene definito il contratto di servizio:</span><span class="sxs-lookup"><span data-stu-id="024b7-161">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

<span data-ttu-id="024b7-162">Una classe che implementa un contratto di servizio viene definita tipo di servizio in WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-162">A class that implements a service contract is referred to as a service type in WCF.</span></span>

<span data-ttu-id="024b7-163">Il passaggio successivo consiste nell'associare un indirizzo e un'associazione a un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-163">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="024b7-164">Questa operazione viene in genere eseguita in un file di configurazione, modificando direttamente il file o usando un editor di configurazione fornito con WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-164">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with WCF.</span></span> <span data-ttu-id="024b7-165">Di seguito è riportato un esempio di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-165">Here is an example of a configuration file.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
     <system.serviceModel>
      <services>
      <service name="Service ">
       <endpoint
        address="EchoService"
        binding="basicHttpBinding"
        contract="IEchoService "/>
      </service>
      </services>
     </system.serviceModel>
</configuration>
```

<span data-ttu-id="024b7-166">L'associazione specifica il set di protocolli per la comunicazione con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-166">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="024b7-167">Nella tabella seguente sono elencate le associazioni fornite dal sistema che rappresentano opzioni comuni.</span><span class="sxs-lookup"><span data-stu-id="024b7-167">The following table lists the system-provided bindings that represent common options.</span></span>

|<span data-ttu-id="024b7-168">Nome</span><span class="sxs-lookup"><span data-stu-id="024b7-168">Name</span></span>|<span data-ttu-id="024b7-169">Scopo</span><span class="sxs-lookup"><span data-stu-id="024b7-169">Purpose</span></span>|
|----------|-------------|
|<span data-ttu-id="024b7-170">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-170">BasicHttpBinding</span></span>|<span data-ttu-id="024b7-171">Interoperabilità con servizi Web e client che supportano WS-BasicProfile 1.1 e Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="024b7-171">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|
|<span data-ttu-id="024b7-172">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-172">WSHttpBinding</span></span>|<span data-ttu-id="024b7-173">Interoperabilità con servizi Web e client che supportano protocolli WS-\* su HTTP.</span><span class="sxs-lookup"><span data-stu-id="024b7-173">Interoperability with Web services and clients that support the WS-\* protocols over HTTP.</span></span>|
|<span data-ttu-id="024b7-174">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-174">WSDualHttpBinding</span></span>|<span data-ttu-id="024b7-175">Comunicazione HTTP duplex in base alla quale il ricevitore di un messaggio iniziale non risponde direttamente al mittente iniziale, ma può trasmettere un numero qualsiasi di risposte in un determinato periodo di tempo usando HTTP in conformità ai protocolli WS-\*.</span><span class="sxs-lookup"><span data-stu-id="024b7-175">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-\* protocols.</span></span>|
|<span data-ttu-id="024b7-176">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-176">WSFederationBinding</span></span>|<span data-ttu-id="024b7-177">Comunicazione HTTP nella quale l'accesso alle risorse di un servizio può essere controllato in base a credenziali rilasciate da un provider di credenziali identificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="024b7-177">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|
|<span data-ttu-id="024b7-178">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-178">NetTcpBinding</span></span>|<span data-ttu-id="024b7-179">Comunicazione sicura, affidabile e a elevate prestazioni tra entità software WCF in una rete.</span><span class="sxs-lookup"><span data-stu-id="024b7-179">Secure, reliable, high-performance communication between WCF software entities across a network.</span></span>|
|<span data-ttu-id="024b7-180">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-180">NetNamedPipeBinding</span></span>|<span data-ttu-id="024b7-181">Comunicazione sicura, affidabile e a elevate prestazioni tra entità software WCF nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="024b7-181">Secure, reliable, high-performance communication between WCF software entities on the same machine.</span></span>|
|<span data-ttu-id="024b7-182">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-182">NetMsmqBinding</span></span>|<span data-ttu-id="024b7-183">Comunicazione tra entità software WCF tramite MSMQ.</span><span class="sxs-lookup"><span data-stu-id="024b7-183">Communication between WCF software entities by using MSMQ.</span></span>|
|<span data-ttu-id="024b7-184">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-184">MsmqIntegrationBinding</span></span>|<span data-ttu-id="024b7-185">Comunicazione tra un'entità software WCF e un'altra entità software tramite MSMQ.</span><span class="sxs-lookup"><span data-stu-id="024b7-185">Communication between a WCF software entity and another software entity by using MSMQ.</span></span>|
|<span data-ttu-id="024b7-186">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="024b7-186">NetPeerTcpBinding</span></span>|<span data-ttu-id="024b7-187">Comunicazione tra entità software WCF mediante la rete peer-to-peer di Windows.</span><span class="sxs-lookup"><span data-stu-id="024b7-187">Communication between WCF software entities by using Windows Peer-to-Peer Networking.</span></span>|

<span data-ttu-id="024b7-188">L'associazione fornita dal sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora il set di protocolli supportato dai servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-188">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>

<span data-ttu-id="024b7-189">Le associazioni personalizzate per le applicazioni WCF sono facilmente definite come raccolte delle classi di elementi di associazione utilizzate da WCF per implementare i singoli protocolli.</span><span class="sxs-lookup"><span data-stu-id="024b7-189">Custom bindings for WCF applications are easily defined as collections of the binding element classes that WCF uses to implement individual protocols.</span></span> <span data-ttu-id="024b7-190">Nuovi elementi di associazione possono essere scritti per rappresentare protocolli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="024b7-190">New binding elements can be written to represent additional protocols.</span></span>

<span data-ttu-id="024b7-191">Il comportamento interno dei tipi di servizio può essere regolato usando le proprietà di una famiglia di classi denominate comportamenti.</span><span class="sxs-lookup"><span data-stu-id="024b7-191">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="024b7-192">In questo caso la classe <xref:System.ServiceModel.ServiceBehaviorAttribute> viene usata per specificare che il tipo di servizio deve essere multithreading.</span><span class="sxs-lookup"><span data-stu-id="024b7-192">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple)]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

<span data-ttu-id="024b7-193">Alcuni comportamenti, come <xref:System.ServiceModel.ServiceBehaviorAttribute>, sono attributi.</span><span class="sxs-lookup"><span data-stu-id="024b7-193">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="024b7-194">I comportamenti con proprietà che gli amministratori vorrebbero impostare possono essere modificati nella configurazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-194">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>

<span data-ttu-id="024b7-195">Nella programmazione di tipi di servizio viene spesso usata la classe <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="024b7-195">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="024b7-196">La proprietà <xref:System.ServiceModel.OperationContext.Current%2A> statica di questa classe fornisce l'accesso a informazioni sul contesto nel quale viene eseguita un'operazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-196">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="024b7-197">L'oggetto <xref:System.ServiceModel.OperationContext> è simile a entrambe le classi <xref:System.Web.HttpContext> e <xref:System.EnterpriseServices.ContextUtil>.</span><span class="sxs-lookup"><span data-stu-id="024b7-197"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>

## <a name="hosting"></a><span data-ttu-id="024b7-198">Hosting</span><span class="sxs-lookup"><span data-stu-id="024b7-198">Hosting</span></span>

<span data-ttu-id="024b7-199">I servizi Web ASP.NET vengono compilati in un assembly della libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="024b7-199">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="024b7-200">Viene fornito un file denominato file del servizio che ha l'estensione asmx e contiene una direttiva `@ WebService` che identifica la classe che contiene il codice per il servizio e l'assembly in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="024b7-200">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>

`<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>`

<span data-ttu-id="024b7-201">Il file del servizio viene copiato in una radice dell'applicazione ASP.NET in Internet Information Services (IIS) e l'assembly viene copiato nella sottodirectory \bin di tale radice.</span><span class="sxs-lookup"><span data-stu-id="024b7-201">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="024b7-202">Per accedere all'applicazione sarà quindi possibile usare l'URL (Uniform Resource Locator) del file del servizio nella radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-202">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>

<span data-ttu-id="024b7-203">I servizi WCF possono essere ospitati immediatamente in IIS 5,1 o 6,0, il servizio di attivazione dei processi di Windows (WAS) fornito come parte di IIS 7,0 e in qualsiasi applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-203">WCF services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="024b7-204">Per ospitare un servizio in IIS 5.1 o 6.0 il servizio deve usare HTTP come protocollo di trasporto delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="024b7-204">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>

<span data-ttu-id="024b7-205">Per ospitare un servizio in IIS 5.1, 6.0 o in WAS, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="024b7-205">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>

1. <span data-ttu-id="024b7-206">Compilare il tipo di servizio in un assembly della libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="024b7-206">Compile the service type into a class library assembly.</span></span>

2. <span data-ttu-id="024b7-207">Creare un file del servizio con un'estensione svc con una direttiva `@ ServiceHost` per identificare il tipo di servizio:</span><span class="sxs-lookup"><span data-stu-id="024b7-207">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>

    `<%@ServiceHost language="c#" Service="MyService" %>`

3. <span data-ttu-id="024b7-208">Copiare il file del servizio in una directory virtuale e l'assembly nella sottodirectory \bin di tale directory.</span><span class="sxs-lookup"><span data-stu-id="024b7-208">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>

4. <span data-ttu-id="024b7-209">Copiare il file di configurazione nella directory virtuale e denominarlo Web.config.</span><span class="sxs-lookup"><span data-stu-id="024b7-209">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>

<span data-ttu-id="024b7-210">Per accedere all'applicazione sarà quindi possibile usare l'URL del file del servizio nella radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-210">The application is then accessible by using the URL of the service file in the application root.</span></span>

<span data-ttu-id="024b7-211">Per ospitare un servizio WCF all'interno di un'applicazione .NET, compilare il tipo di servizio in un assembly della libreria di classi a cui fa riferimento l'applicazione e programmare l'applicazione in modo che ospiti il servizio usando la <xref:System.ServiceModel.ServiceHost> classe.</span><span class="sxs-lookup"><span data-stu-id="024b7-211">To host a WCF service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="024b7-212">Di seguito è riportato un esempio della programmazione di base necessaria.</span><span class="sxs-lookup"><span data-stu-id="024b7-212">The following is an example of the basic programming required:</span></span>

```csharp
string httpBaseAddress = "http://www.contoso.com:8000/";
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";

Uri httpBaseAddressUri = new Uri(httpBaseAddress);
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);

Uri[] baseAddresses = new Uri[] {
 httpBaseAddressUri,
 tcpBaseAddressUri};

using(ServiceHost host = new ServiceHost(
typeof(Service), //"Service" is the name of the service type baseAddresses))
{
     host.Open();

     […] //Wait to receive messages
     host.Close();
}
```

<span data-ttu-id="024b7-213">Questo esempio mostra in che modo vengono specificati gli indirizzi per uno o più protocolli di trasporto nella costruzione di una classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="024b7-213">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="024b7-214">Questi indirizzi sono detti indirizzi di base.</span><span class="sxs-lookup"><span data-stu-id="024b7-214">These addresses are referred to as base addresses.</span></span>

<span data-ttu-id="024b7-215">L'indirizzo fornito per qualsiasi endpoint di un servizio WCF è un indirizzo relativo a un indirizzo di base dell'host dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="024b7-215">The address provided for any endpoint of a WCF service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="024b7-216">L'host può avere un indirizzo di base per ogni protocollo di trasporto della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-216">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="024b7-217">Nella configurazione di esempio nel file di configurazione precedente, il costruttore <xref:System.ServiceModel.BasicHttpBinding> selezionato per l'endpoint usa HTTP come protocollo di trasporto. L'indirizzo dell'endpoint, `EchoService` è quindi relativo all'indirizzo di base HTTP dell'host.</span><span class="sxs-lookup"><span data-stu-id="024b7-217">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="024b7-218">Nel caso dell'host nell'esempio precedente, l'indirizzo di base HTTP è `http://www.contoso.com:8000/` .</span><span class="sxs-lookup"><span data-stu-id="024b7-218">In the case of the host in the preceding example, the HTTP base address is `http://www.contoso.com:8000/`.</span></span> <span data-ttu-id="024b7-219">Nel caso di un servizio ospitato in IIS o WAS, l'indirizzo di base è l'URL del file del servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-219">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>

<span data-ttu-id="024b7-220">Solo i servizi ospitati in IIS o WAS e che sono configurati solo con HTTP come protocollo di trasporto, possono essere eseguiti per utilizzare l'opzione modalità di compatibilità ASP.NET di WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-220">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use WCF ASP.NET compatibility mode option.</span></span> <span data-ttu-id="024b7-221">Per attivare questa opzione è necessario eseguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="024b7-221">Turning that option on requires the following steps.</span></span>

1. <span data-ttu-id="024b7-222">Il programmatore deve aggiungere l'attributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo di servizio e deve specificare che la modalità di compatibilità ASP.NET è consentita o necessaria.</span><span class="sxs-lookup"><span data-stu-id="024b7-222">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. <span data-ttu-id="024b7-223">L'amministratore deve configurare l'applicazione per l'uso della modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-223">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>

    ```xml
    <configuration>
         <system.serviceModel>
          <services>
          […]
          </services>
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
        </system.serviceModel>
    </configuration>
    ```

    <span data-ttu-id="024b7-224">Le applicazioni WCF possono inoltre essere configurate per l'utilizzo di. asmx come estensione per i file del servizio anziché con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="024b7-224">WCF applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>

    ```xml
    <system.web>
         <compilation>
          <compilation debug="true">
          <buildProviders>
           <remove extension=".asmx"/>
           <add extension=".asmx"
            type="System.ServiceModel.ServiceBuildProvider,
            System.ServiceModel,
            Version=3.0.0.0,
            Culture=neutral,
            PublicKeyToken=b77a5c561934e089" />
          </buildProviders>
          </compilation>
         </compilation>
    </system.web>
    ```

    <span data-ttu-id="024b7-225">Questa opzione consente di evitare di dover modificare i client configurati per l'utilizzo degli URL dei file del servizio ASMX quando si modifica un servizio per l'utilizzo di WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-225">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use WCF.</span></span>

## <a name="client-development"></a><span data-ttu-id="024b7-226">Sviluppo client</span><span class="sxs-lookup"><span data-stu-id="024b7-226">Client Development</span></span>

<span data-ttu-id="024b7-227">I client per i servizi Web ASP.NET vengono generati usando lo strumento da riga di comando WSDL.exe che fornisce come input l'URL del file con estensione asmx.</span><span class="sxs-lookup"><span data-stu-id="024b7-227">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="024b7-228">Lo strumento corrispondente fornito da WCF è [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="024b7-228">The corresponding tool provided by WCF is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="024b7-229">Genera un modulo di codice con la definizione del contratto di servizio e la definizione di una classe client WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-229">It generates a code module with the definition of the service contract and the definition of a WCF client class.</span></span> <span data-ttu-id="024b7-230">Genera anche un file di configurazione con l'indirizzo e l'associazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-230">It also generates a configuration file with the address and binding of the service.</span></span>

<span data-ttu-id="024b7-231">Per programmare un client per un servizio remoto è in genere consigliabile eseguire la programmazione in base a un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="024b7-231">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="024b7-232">Il codice generato dallo strumento WSDL.exe fornisce sempre per entrambi un modello sincrono e un modello asincrono per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="024b7-232">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="024b7-233">Il codice generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può fornire per uno dei due modelli.</span><span class="sxs-lookup"><span data-stu-id="024b7-233">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="024b7-234">Per impostazione predefinita viene usato per il modello sincrono.</span><span class="sxs-lookup"><span data-stu-id="024b7-234">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="024b7-235">Se lo strumento viene eseguito con l'opzione `/async`, il codice generato viene usato per il modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="024b7-235">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>

<span data-ttu-id="024b7-236">Non vi è alcuna garanzia che i nomi nelle classi client WCF generate da ASP. Per impostazione predefinita, lo strumento WSDL. exe di NET corrisponde ai nomi nelle classi client WCF generate dallo strumento Svcutil. exe.</span><span class="sxs-lookup"><span data-stu-id="024b7-236">There is no guarantee that names in the WCF client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in WCF client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="024b7-237">In particolare, nel codice generato dallo strumento Svcutil.exe ai nomi delle proprietà di classi che devono essere serializzate usando la classe <xref:System.Xml.Serialization.XmlSerializer> viene assegnato, per impostazione predefinita, il suffisso Property. Questo non accade invece nel codice generato dallo strumento WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="024b7-237">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>

## <a name="message-representation"></a><span data-ttu-id="024b7-238">Rappresentazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="024b7-238">Message Representation</span></span>

<span data-ttu-id="024b7-239">Le intestazioni dei messaggi SOAP inviati e ricevuti dai servizi Web ASP.NET possono essere personalizzate.</span><span class="sxs-lookup"><span data-stu-id="024b7-239">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="024b7-240">Una classe viene derivata dalla classe <xref:System.Web.Services.Protocols.SoapHeader> per definire la struttura dell'intestazione. La classe <xref:System.Web.Services.Protocols.SoapHeaderAttribute> viene quindi usata per indicare la presenza dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-240">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>

```csharp
public class SomeProtocol : SoapHeader
{
     public long CurrentValue;
     public long Total;
}

[WebService]
public interface IEcho
{
     SomeProtocol ProtocolHeader
     {
      get;
     set;
     }

     [WebMethod]
     [SoapHeader("ProtocolHeader")]
     string PlaceOrders(PurchaseOrderType order);
}

public class Service: WebService, IEcho
{
     private SomeProtocol protocolHeader;

     public SomeProtocol ProtocolHeader
     {
         get
         {
              return this.protocolHeader;
         }

         set
         {
              this.protocolHeader = value;
         }
     }

     string PlaceOrders(PurchaseOrderType order)
     {
         long currentValue = this.protocolHeader.CurrentValue;
     }
}
```

<span data-ttu-id="024b7-241">WCF fornisce gli attributi,, <xref:System.ServiceModel.MessageContractAttribute> <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute> per descrivere la struttura dei messaggi SOAP inviati e ricevuti da un servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-241">The WCF provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>

```csharp
[DataContract]
public class SomeProtocol
{
     [DataMember]
     public long CurrentValue;
     [DataMember]
     public long Total;
}

[DataContract]
public class Item
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}

[MessageContract]
public class ItemMessage
{
     [MessageHeader]
     public SomeProtocol ProtocolHeader;
     [MessageBody]
     public Item Content;
}

[ServiceContract]
public interface IItemService
{
     [OperationContract]
     public void DeliverItem(ItemMessage itemMessage);
}
```

<span data-ttu-id="024b7-242">Questa sintassi genera una rappresentazione esplicita della struttura dei messaggi, mentre la struttura dei messaggi è implicita nel codice di un servizio Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-242">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="024b7-243">Inoltre, nella sintassi ASP.NET le intestazioni dei messaggi sono rappresentate come proprietà del servizio, ad esempio la `ProtocolHeader` proprietà nell'esempio precedente, mentre nella sintassi WCF sono rappresentate più accuratamente come proprietà dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="024b7-243">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in WCF syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="024b7-244">Inoltre, WCF consente di aggiungere intestazioni di messaggio alla configurazione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="024b7-244">Also, WCF allows message headers to be added to the configuration of endpoints.</span></span>

```xml
<service name="Service ">
     <endpoint
      address="EchoService"
      binding="basicHttpBinding"
      contract="IEchoService ">
      <headers>
      <dsig:X509Certificate
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
       ...
      </dsig:X509Certificate>
      </headers>
     </endpoint>
</service>
```

<span data-ttu-id="024b7-245">Questa opzione consente di evitare qualsiasi riferimento a intestazioni di protocollo infrastrutturali nel codice per un client o un servizio: le intestazioni vengono aggiunte ai messaggi a seconda della modalità di configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="024b7-245">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>

## <a name="service-description"></a><span data-ttu-id="024b7-246">Descrizione del servizio</span><span class="sxs-lookup"><span data-stu-id="024b7-246">Service Description</span></span>

<span data-ttu-id="024b7-247">La pubblicazione di una richiesta HTTP GET per il file asmx di un servizio Web ASP.NET con la query WSDL determina in ASP.NET la generazione del file WSDL per descrivere il servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-247">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="024b7-248">Il file WSDL viene restituito da ASP.NET come risposta alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="024b7-248">It returns that WSDL as the response to the request.</span></span>

<span data-ttu-id="024b7-249">ASP.NET 2.0 consente di verificare che un servizio sia conforme alla specifica Basic Profile 1.1 di WS-I (Web Services-Interoperability Organization ) e di inserire un'attestazione di conformità del servizio nel relativo file WSDL.</span><span class="sxs-lookup"><span data-stu-id="024b7-249">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="024b7-250">Questa verifica viene effettuata usando i parametri `ConformsTo` e `EmitConformanceClaims` dell'attributo <xref:System.Web.Services.WebServiceBindingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="024b7-250">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

<span data-ttu-id="024b7-251">Il WSDL generato da ASP.NET per un servizio può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="024b7-251">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="024b7-252">Le personalizzazioni vengono effettuate creando una classe derivata di <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> per aggiungere elementi al WSDL.</span><span class="sxs-lookup"><span data-stu-id="024b7-252">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>

<span data-ttu-id="024b7-253">L'invio di una richiesta HTTP GET con la query WSDL per il file con estensione svc di un servizio WCF con un endpoint HTTP ospitato in IIS 51, 6,0 o WAS fa sì che WCF risponda con WSDL per descrivere il servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-253">Issuing an HTTP GET request with the query WSDL for the .svc file of a WCF service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes WCF to respond with WSDL to describe the service.</span></span> <span data-ttu-id="024b7-254">L'invio di una richiesta GET HTTP con la query WSDL all'indirizzo di base HTTP di un servizio ospitato in un'applicazione .NET produce lo stesso effetto di quando httpGetEnabled è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="024b7-254">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>

<span data-ttu-id="024b7-255">Tuttavia, WCF risponde anche alle richieste WS-MetadataExchange con WSDL generato per descrivere un servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-255">However, WCF also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="024b7-256">I servizi Web ASP.NET non dispongono di supporto incorporato per le richieste WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="024b7-256">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>

<span data-ttu-id="024b7-257">Il WSDL generato da WCF può essere ampiamente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="024b7-257">The WSDL that WCF generates can be extensively customized.</span></span> <span data-ttu-id="024b7-258">La classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> fornisce alcune funzioni per la personalizzazione di WSDL.</span><span class="sxs-lookup"><span data-stu-id="024b7-258">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="024b7-259">WCF può anche essere configurato in modo da non generare WSDL, bensì usare un file WSDL statico in un URL specificato.</span><span class="sxs-lookup"><span data-stu-id="024b7-259">The WCF can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>

```xml
<behaviors>
     <behavior name="DescriptionBehavior">
     <metadataPublishing
      enableMetadataExchange="true"
      enableGetWsdl="true"
      enableHelpPage="true"
      metadataLocation=
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>
     </behavior>
</behaviors>
```

## <a name="exception-handling"></a><span data-ttu-id="024b7-260">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="024b7-260">Exception Handling</span></span>

<span data-ttu-id="024b7-261">Nei servizi Web ASP.NET le eccezioni non gestite vengono restituite ai client come errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="024b7-261">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="024b7-262">È anche possibile generare esplicitamente istanze della classe <xref:System.Web.Services.Protocols.SoapException> e disporre di maggiore controllo sul contenuto dell'errore SOAP che viene trasmesso al client.</span><span class="sxs-lookup"><span data-stu-id="024b7-262">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>

<span data-ttu-id="024b7-263">Nei servizi WCF, le eccezioni non gestite non vengono restituite ai client come errori SOAP per impedire che le informazioni riservate vengano inavvertitamente esposte tramite le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="024b7-263">In WCF services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="024b7-264">Viene fornita un'impostazione di configurazione per fare in modo che le eccezioni non gestite vengano restituite ai client a scopo di debug.</span><span class="sxs-lookup"><span data-stu-id="024b7-264">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>

<span data-ttu-id="024b7-265">Per restituire gli errori SOAP ai client è possibile generare istanze del tipo generico, <xref:System.ServiceModel.FaultException%601>, usando il tipo di contratto dati come tipo generico.</span><span class="sxs-lookup"><span data-stu-id="024b7-265">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="024b7-266">È anche possibile aggiungere attributi <xref:System.ServiceModel.FaultContractAttribute> alle operazioni per specificare gli errori che un'operazione potrebbe generare.</span><span class="sxs-lookup"><span data-stu-id="024b7-266">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>

```csharp
[DataContract]
public class MathFault
{
     [DataMember]
     public string operation;
     [DataMember]
     public string problemType;
}

[ServiceContract]
public interface ICalculator
{
     [OperationContract]
     [FaultContract(typeof(MathFault))]
     int Divide(int n1, int n2);
}
```

<span data-ttu-id="024b7-267">In questo modo i potenziali errori vengono annunciati nel WSDL per il servizio, consentendo ai programmatori dei client di prevedere quali errori potrebbero risultare da un'operazione e di scrivere le istruzioni Catch appropriate.</span><span class="sxs-lookup"><span data-stu-id="024b7-267">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>

```csharp
try
{
     result = client.Divide(value1, value2);
}
catch (FaultException<MathFault> e)
{
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "
  + e.Detail.operation
  + ". Problem: "
  + e.Detail.problemType);
}
```

## <a name="state-management"></a><span data-ttu-id="024b7-268">Gestione dello stato</span><span class="sxs-lookup"><span data-stu-id="024b7-268">State Management</span></span>

<span data-ttu-id="024b7-269">La classe usata per implementare un servizio Web ASP.NET può essere derivata da <xref:System.Web.Services.WebService>.</span><span class="sxs-lookup"><span data-stu-id="024b7-269">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

<span data-ttu-id="024b7-270">In tal caso, la classe può essere programmata per usare la proprietà Context della classe di base <xref:System.Web.Services.WebService> per accedere a un oggetto <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="024b7-270">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="024b7-271">L'oggetto <xref:System.Web.HttpContext> può essere usato per aggiornare e recuperare informazioni sullo stato dell'applicazione usando la relativa proprietà Application, nonché per aggiornare e recuperare informazioni sullo stato della sessione usando la relativa proprietà Session.</span><span class="sxs-lookup"><span data-stu-id="024b7-271">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>

<span data-ttu-id="024b7-272">ASP.NET fornisce un livello di controllo elevato sulla posizione in cui vengono effettivamente memorizzate le informazioni sullo stato della sessione alla quali è possibile accedere usando la proprietà Session dell'oggetto <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="024b7-272">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="024b7-273">Possono essere memorizzate in cookie, in un database, nella memoria del server corrente o nella memoria di un server specificato.</span><span class="sxs-lookup"><span data-stu-id="024b7-273">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="024b7-274">La scelta viene effettuata nel file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-274">The choice is made in the service’s configuration file.</span></span>

<span data-ttu-id="024b7-275">WCF fornisce oggetti estendibili per la gestione dello stato.</span><span class="sxs-lookup"><span data-stu-id="024b7-275">The WCF provides extensible objects for state management.</span></span> <span data-ttu-id="024b7-276">Gli oggetti estensibili sono oggetti che implementano l'interfaccia <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="024b7-276">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="024b7-277">Gli oggetti estendibili più importanti sono <xref:System.ServiceModel.ServiceHostBase> e <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="024b7-277">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="024b7-278">`ServiceHostBase` consente di mantenere lo stato al quale possono accedere tutte le istanze di tutti i tipi di servizio sullo stesso host, mentre `InstanceContext` consente di mantenere lo stato al quale può accedere qualsiasi codice in esecuzione nella stessa istanza di un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-278">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>

<span data-ttu-id="024b7-279">Qui, il tipo di servizio, `TradingSystem` , dispone di un oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute> che specifica che tutte le chiamate dalla stessa istanza del client WCF vengono instradate alla stessa istanza del tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-279">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same WCF client instance are routed to the same instance of the service type.</span></span>

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

<span data-ttu-id="024b7-280">La classe `DealData` definisce lo stato al quale può accedere qualsiasi codice in esecuzione nella stessa istanza di un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-280">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

<span data-ttu-id="024b7-281">Nel codice del tipo di servizio che implementa una delle operazioni del contratto di servizio viene aggiunto un oggetto stato `DealData` allo stato dell'istanza corrente del tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-281">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

<span data-ttu-id="024b7-282">Questo oggetto stato può essere successivamente recuperato e modificato dal codice che implementa un'altra delle operazioni del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="024b7-282">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

<span data-ttu-id="024b7-283">Mentre ASP.NET fornisce il controllo sulla posizione in cui vengono archiviate le informazioni sullo stato nella <xref:System.Web.HttpContext> classe, WCF, almeno nella versione iniziale, non fornisce alcun controllo sulla posizione in cui vengono archiviati gli oggetti estensibili.</span><span class="sxs-lookup"><span data-stu-id="024b7-283">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, WCF, at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="024b7-284">Questo costituisce il motivo migliore per la selezione della modalità di compatibilità ASP.NET per un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-284">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a WCF service.</span></span> <span data-ttu-id="024b7-285">Se la gestione dello stato configurabile è imperativa, la scelta della modalità di compatibilità ASP.NET consente di usare le funzioni della classe <xref:System.Web.HttpContext> esattamente nel modo in cui vengono usate in ASP.NET, nonché di configurare la posizione in cui vengono memorizzate le informazioni sullo stato gestite mediante la classe <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="024b7-285">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>

## <a name="security"></a><span data-ttu-id="024b7-286">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="024b7-286">Security</span></span>

<span data-ttu-id="024b7-287">Le opzioni per la protezione dei servizi Web ASP.NET sono le stesse usate per la protezione di qualsiasi applicazione IIS.</span><span class="sxs-lookup"><span data-stu-id="024b7-287">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="024b7-288">Poiché le applicazioni WCF possono essere ospitate non solo in IIS ma anche in qualsiasi eseguibile .NET, le opzioni per la protezione delle applicazioni WCF devono essere rese indipendenti dalle funzionalità di IIS.</span><span class="sxs-lookup"><span data-stu-id="024b7-288">Because WCF applications can be hosted not only within IIS but also within any .NET executable, the options for securing WCF applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="024b7-289">Tuttavia, le funzionalità fornite per i servizi Web ASP.NET sono disponibili anche per i servizi WCF in esecuzione in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-289">However, the facilities provided for ASP.NET Web services are also available for WCF services running in ASP.NET compatibility mode.</span></span>

### <a name="security-authentication"></a><span data-ttu-id="024b7-290">Protezione: autenticazione</span><span class="sxs-lookup"><span data-stu-id="024b7-290">Security: Authentication</span></span>

<span data-ttu-id="024b7-291">IIS fornisce funzionalità per il controllo di accesso alle applicazioni tra le quali è possibile selezionare l'accesso anonimo o varie modalità di autenticazione: autenticazione di Windows, autenticazione digest, autenticazione di base e autenticazione .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="024b7-291">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="024b7-292">L'opzione Autenticazione di Windows può essere usata per controllare l'accesso ai servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-292">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="024b7-293">Tuttavia, quando le applicazioni WCF sono ospitate in IIS, è necessario configurare IIS per consentire l'accesso anonimo all'applicazione, in modo che l'autenticazione possa essere gestita da WCF, che supporta l'autenticazione di Windows tra le varie opzioni.</span><span class="sxs-lookup"><span data-stu-id="024b7-293">However, when WCF applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by WCF itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="024b7-294">Le altre opzioni incorporate includono token del nome utente, certificati X.509, token SAML e schede CardSpace, ma è comunque possibile definire meccanismi di autenticazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="024b7-294">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>

### <a name="security-impersonation"></a><span data-ttu-id="024b7-295">Protezione: rappresentazione</span><span class="sxs-lookup"><span data-stu-id="024b7-295">Security: Impersonation</span></span>

<span data-ttu-id="024b7-296">ASP.NET fornisce un elemento di identità mediante il quale un servizio Web ASP.NET può essere impostato per rappresentare un determinato utente o le credenziali utente che vengono fornite con la richiesta corrente.</span><span class="sxs-lookup"><span data-stu-id="024b7-296">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="024b7-297">Tale elemento può essere utilizzato per configurare la rappresentazione nelle applicazioni WCF in esecuzione in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-297">That element can be used to configure impersonation in WCF applications running in ASP.NET compatibility mode.</span></span>

<span data-ttu-id="024b7-298">Il sistema di configurazione WCF fornisce il proprio elemento Identity per la designazione di un utente specifico per la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-298">The WCF configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="024b7-299">Inoltre, i client e i servizi WCF possono essere configurati in modo indipendente per la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-299">Also, WCF clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="024b7-300">I client possono essere configurati per rappresentare l'utente corrente quando trasmettono richieste.</span><span class="sxs-lookup"><span data-stu-id="024b7-300">Clients can be configured to impersonate the current user when they transmit requests.</span></span>

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

<span data-ttu-id="024b7-301">Le operazioni dei servizi possono essere configurate per rappresentare le credenziali utente fornite con la richiesta corrente.</span><span class="sxs-lookup"><span data-stu-id="024b7-301">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="024b7-302">Protezione: autorizzazione mediante elenchi di controllo di accesso (ACL)</span><span class="sxs-lookup"><span data-stu-id="024b7-302">Security: Authorization using Access Control Lists</span></span>

<span data-ttu-id="024b7-303">Gli elenchi di controllo di accesso (ACL) possono essere usati per limitare l'accesso ai file con estensione asmx.</span><span class="sxs-lookup"><span data-stu-id="024b7-303">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="024b7-304">Tuttavia, gli ACL nei file WCF. svc vengono ignorati tranne che in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-304">However, ACLs on WCF .svc files are ignored except in ASP.NET compatibility mode.</span></span>

### <a name="security-role-based-authorization"></a><span data-ttu-id="024b7-305">Protezione: autorizzazione basata sui ruoli</span><span class="sxs-lookup"><span data-stu-id="024b7-305">Security: Role-based Authorization</span></span>

<span data-ttu-id="024b7-306">L'opzione Autenticazione di Windows di IIS può essere usata insieme all'elemento di autorizzazione fornito dal linguaggio di configurazione di ASP.NET per facilitare l'autorizzazione basata sui ruoli per i servizi Web ASP.NET basati sui gruppi di Windows ai quali sono assegnati gli utenti.</span><span class="sxs-lookup"><span data-stu-id="024b7-306">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="024b7-307">ASP.NET 2.0 ha introdotto un meccanismo più generale di autorizzazione basata sui ruoli: i provider di ruoli.</span><span class="sxs-lookup"><span data-stu-id="024b7-307">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>

<span data-ttu-id="024b7-308">I provider di ruoli sono classi che implementano tutte un'interfaccia di base per ottenere informazioni sui ruoli ai quali è assegnato un utente, ma ogni provider di ruoli sa come recuperare tali informazioni da un'origine diversa.</span><span class="sxs-lookup"><span data-stu-id="024b7-308">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="024b7-309">ASP.NET 2.0 fornisce un provider di ruoli in grado di recuperare assegnazioni di ruolo da un database Microsoft SQL Server e un altro provider in grado di recuperare assegnazioni di ruolo da Gestione autorizzazioni di Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="024b7-309">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>

<span data-ttu-id="024b7-310">Il meccanismo del provider di ruoli può essere effettivamente utilizzato indipendentemente da ASP.NET in qualsiasi applicazione .NET, inclusa un'applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="024b7-310">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a WCF application.</span></span> <span data-ttu-id="024b7-311">La configurazione di esempio seguente per un'applicazione WCF Mostra come l'uso di un provider di ruoli ASP.NET è un'opzione selezionata per mezzo del <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .</span><span class="sxs-lookup"><span data-stu-id="024b7-311">The following sample configuration for a WCF application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>

```xml
<system.serviceModel>
     <services>
         <service name="Service.ResourceAccessServiceType"
             behaviorConfiguration="ServiceBehavior">
             <endpoint
              address="ResourceAccessService"
              binding="wsHttpBinding"
              contract="Service.IResourceAccessContract"/>
         </service>
     </services>
     <behaviors>
       <behavior name="ServiceBehavior">
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
      </behavior>
     </behaviors>
</system.serviceModel>
```

### <a name="security-claims-based-authorization"></a><span data-ttu-id="024b7-312">Protezione: autorizzazione basata sulle attestazioni</span><span class="sxs-lookup"><span data-stu-id="024b7-312">Security: Claims-based Authorization</span></span>

<span data-ttu-id="024b7-313">Una delle innovazioni più importanti di WCF è il supporto completo per l'autorizzazione dell'accesso alle risorse protette in base alle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="024b7-313">One of the most important innovations of WCF is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="024b7-314">Le attestazioni sono costituite da un tipo, da un diritto e da un valore, ad esempio la licenza di un driver.</span><span class="sxs-lookup"><span data-stu-id="024b7-314">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="024b7-315">In questo caso WCF crea un set di attestazioni relative al titolare della licenza, una delle quali è la data di nascita del titolare.</span><span class="sxs-lookup"><span data-stu-id="024b7-315">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="024b7-316">Il tipo di questa attestazione è data di nascita, mentre il valore dell'attestazione è la data di nascita del titolare della licenza.</span><span class="sxs-lookup"><span data-stu-id="024b7-316">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="024b7-317">Il diritto che un'attestazione conferisce al titolare specifica le operazioni che possono essere eseguite dal titolare con il valore dell'attestazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-317">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="024b7-318">Nel caso dell'attestazione della data di nascita del titolare della licenza, il diritto è possesso: il titolare possiede quella data di nascita ma non può, ad esempio, modificarla.</span><span class="sxs-lookup"><span data-stu-id="024b7-318">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="024b7-319">L'autorizzazione basata sulle attestazioni include l'autorizzazione basata sui ruoli in quanto i ruoli sono un tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-319">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>

<span data-ttu-id="024b7-320">L'autorizzazione basata sulle attestazioni viene eseguita confrontando un set di attestazioni ai requisiti di accesso dell'operazione e, a seconda del risultato di tale confronto, concedendo o negando l'accesso all'operazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-320">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="024b7-321">In WCF è possibile specificare una classe da utilizzare per eseguire l'autorizzazione basata sulle attestazioni, ancora una volta assegnando un valore alla `ServiceAuthorizationManager` proprietà di <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .</span><span class="sxs-lookup"><span data-stu-id="024b7-321">In WCF, you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

<span data-ttu-id="024b7-322">Le classi usate per eseguire l'autorizzazione basata sulle attestazioni devono derivare da <xref:System.ServiceModel.ServiceAuthorizationManager>, che deve eseguire l'override di un solo metodo, `AccessCheck()`.</span><span class="sxs-lookup"><span data-stu-id="024b7-322">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> <span data-ttu-id="024b7-323">WCF chiama tale metodo ogni volta che viene richiamata un'operazione del servizio e fornisce un <xref:System.ServiceModel.OperationContext> oggetto che dispone delle attestazioni per l'utente nella relativa `ServiceSecurityContext.AuthorizationContext` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="024b7-323">WCF calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> <span data-ttu-id="024b7-324">WCF esegue le operazioni di assemblaggio delle attestazioni relative all'utente da qualsiasi token di sicurezza fornito dall'utente per l'autenticazione, che lascia l'attività di valutazione del fatto che le attestazioni siano sufficienti per l'operazione in questione.</span><span class="sxs-lookup"><span data-stu-id="024b7-324">WCF does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>

<span data-ttu-id="024b7-325">Che WCF assembla automaticamente le attestazioni da qualsiasi tipo di token di sicurezza rappresenta un'innovazione estremamente significativa, perché rende il codice per l'autorizzazione basata sulle attestazioni completamente indipendenti dal meccanismo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="024b7-325">That WCF automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="024b7-326">L'autorizzazione mediante ACL e l'autorizzazione basata sui ruoli in ASP.NET sono invece strettamente collegate all'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="024b7-326">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>

### <a name="security-confidentiality"></a><span data-ttu-id="024b7-327">Protezione: riservatezza</span><span class="sxs-lookup"><span data-stu-id="024b7-327">Security: Confidentiality</span></span>

<span data-ttu-id="024b7-328">La riservatezza dei messaggi scambiati con servizi Web ASP.NET può essere garantita al livello del trasporto configurando l'applicazione in IIS per l'uso del protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="024b7-328">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="024b7-329">È possibile eseguire la stessa operazione per le applicazioni WCF ospitate in IIS.</span><span class="sxs-lookup"><span data-stu-id="024b7-329">The same can be done for WCF applications hosted within IIS.</span></span> <span data-ttu-id="024b7-330">Tuttavia, le applicazioni WCF ospitate al di fuori di IIS possono anche essere configurate per l'utilizzo di un protocollo di trasporto sicuro.</span><span class="sxs-lookup"><span data-stu-id="024b7-330">However, WCF applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="024b7-331">Più importante, le applicazioni WCF possono anche essere configurate per proteggere i messaggi prima che vengano trasportati, utilizzando il protocollo WS-Security.</span><span class="sxs-lookup"><span data-stu-id="024b7-331">More important, WCF applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="024b7-332">La protezione del solo corpo del messaggio mediante il protocollo WS-Security consente la trasmissione riservata del messaggio su intermediari prima di raggiungere la destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="024b7-332">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>

## <a name="globalization"></a><span data-ttu-id="024b7-333">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="024b7-333">Globalization</span></span>

<span data-ttu-id="024b7-334">Il linguaggio di configurazione di ASP.NET consente di specificare le impostazioni cultura per i singoli servizi.</span><span class="sxs-lookup"><span data-stu-id="024b7-334">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="024b7-335">WCF non supporta questa impostazione di configurazione tranne che in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="024b7-335">The WCF does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="024b7-336">Per localizzare un servizio WCF che non usa la modalità di compatibilità ASP.NET, compilare il tipo di servizio in assembly specifici delle impostazioni cultura e avere endpoint specifici delle impostazioni cultura per ogni assembly specifico delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="024b7-336">To localize a WCF service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="024b7-337">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="024b7-337">See also</span></span>

- [<span data-ttu-id="024b7-338">Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati</span><span class="sxs-lookup"><span data-stu-id="024b7-338">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
