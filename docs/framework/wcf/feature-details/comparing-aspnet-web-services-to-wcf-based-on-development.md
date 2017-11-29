---
title: Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 82fb1848fc329db2921b626a894b9f91e766cd30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="d7bcd-102">Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo</span><span class="sxs-lookup"><span data-stu-id="d7bcd-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d7bcd-103"> include un'opzione della modalità compatibilità ASP.NET che consente alle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di essere programmate e configurate come servizi Web ASP.NET e riprodurne il comportamento.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-103"> has an ASP.NET compatibility mode option to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="d7bcd-104">Nelle sezioni seguenti viene eseguito un confronto tra servizi Web ASP.NET e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basato sugli elementi necessari per lo sviluppo di applicazioni usando entrambe le tecnologie.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-104">The following sections compare ASP.NET Web services and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] based on what is required to develop applications using both technologies.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="d7bcd-105">Rappresentazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d7bcd-105">Data Representation</span></span>  
 <span data-ttu-id="d7bcd-106">Lo sviluppo di un servizio Web con ASP.NET inizia in genere con la definizione di qualsiasi tipo di dati complesso che il servizio deve usare.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="d7bcd-107">ASP.NET si basa sulla classe <xref:System.Xml.Serialization.XmlSerializer> per tradurre dati rappresentati da tipi .NET Framework in dati XML per la trasmissione a o da un servizio, nonché per tradurre dati ricevuti come XML in oggetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="d7bcd-108">La definizione dei tipi di dati complessi che un servizio ASP.NET deve usare richiede la definizione di classi .NET Framework che la classe <xref:System.Xml.Serialization.XmlSerializer> può serializzare in e da XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="d7bcd-109">Tali classi possono essere scritte manualmente o generate da definizioni dei tipi in XML Schema usando l'utilità della riga di comando XML Schemas/Data Types Support Utility, xsd.exe.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>  
  
 <span data-ttu-id="d7bcd-110">Di seguito sono elencati i principali aspetti da considerare nella definizione di classi .NET Framework che la classe <xref:System.Xml.Serialization.XmlSerializer> può serializzare in XML e da XML:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>  
  
-   <span data-ttu-id="d7bcd-111">Soltanto i campi e le proprietà pubbliche di oggetti .NET Framework vengono tradotti in XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>  
  
-   <span data-ttu-id="d7bcd-112">Le istanze di classi di raccolte possono essere serializzate in XML soltanto se le classi implementano l'interfaccia <xref:System.Collections.IEnumerable> o <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>  
  
-   <span data-ttu-id="d7bcd-113">Le classi che implementano l'interfaccia <xref:System.Collections.IDictionary>, ad esempio <xref:System.Collections.Hashtable>, non possono essere serializzate in XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>  
  
-   <span data-ttu-id="d7bcd-114">I numerosi tipi di attributo nello spazio dei nomi <xref:System.Xml.Serialization> possono essere aggiunti a una classe .NET Framework e ai relativi membri per controllare in che modo le istanze della classe vengono rappresentate in XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>  
  
 <span data-ttu-id="d7bcd-115">Anche lo sviluppo di applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] inizia in genere con la definizione di tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application development usually also begins with the definition of complex types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d7bcd-116"> può essere configurato per usare gli stessi tipi .NET Framework dei servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-116"> can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="d7bcd-117">Le classi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> possono essere aggiunte a tipi .NET Framework per indicare che le istanze del tipo devono essere serializzate in XML e quali campi o proprietà specifiche del tipo devono essere serializzate, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>  
  
```  
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
  
 <span data-ttu-id="d7bcd-118"><xref:System.Runtime.Serialization.DataContractAttribute> significa che nessuno dei campi o proprietà di un tipo o altri campi o proprietà di un tipo devono essere serializzati, mentre <xref:System.Runtime.Serialization.DataMemberAttribute> indica che un deve essere serializzato un particolare campo o proprietà.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="d7bcd-119">L'attributo <xref:System.Runtime.Serialization.DataContractAttribute> può essere applicato a una classe o a una struttura.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="d7bcd-120">L'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> può essere applicato a un campo o a una proprietà e i campi e le proprietà alle quali viene applicato l'attributo possono essere pubbliche o private.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="d7bcd-121">In <xref:System.Runtime.Serialization.DataContractAttribute> le istanze di tipi ai quali è applicato l'attributo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono dette contratti dati.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="d7bcd-122">Vengono serializzate in XML usando <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d7bcd-123">Nell'elenco seguente sono descritte le principali differenze tra l'uso di <xref:System.Runtime.Serialization.DataContractSerializer> e l'uso di <xref:System.Xml.Serialization.XmlSerializer> e dei vari attributi dello spazio dei nomi <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>  
  
-   <span data-ttu-id="d7bcd-124">La classe <xref:System.Xml.Serialization.XmlSerializer> e gli attributi dello spazio dei nomi <xref:System.Xml.Serialization> consentono di eseguire il mapping di tipi .NET Framework a qualsiasi tipo valido definito nell'XML Schema e forniscono pertanto un controllo preciso della modalità di rappresentazione di un tipo in XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="d7bcd-125">Gli attributi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> forniscono invece un controllo limitato sulla modalità di rappresentazione di un tipo in XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="d7bcd-126">È possibile specificare soltanto gli spazi dei nomi e i nomi usati per rappresentare il tipo e i relativi campi o proprietà in XML e la sequenza nella quale i campi e le proprietà vengono visualizzate in XML:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>  
  
    ```  
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
  
     <span data-ttu-id="d7bcd-127">Qualsiasi altro elemento relativo alla struttura dell'XML Schema usato per rappresentare il tipo .NET è determinata da <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
-   <span data-ttu-id="d7bcd-128">Non consentendo un controllo esteso sulla modalità di rappresentazione di un tipo in XML, il processo di serializzazione diventa estremamente prevedibile per <xref:System.Runtime.Serialization.DataContractSerializer>e quindi più facile da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="d7bcd-129">Un vantaggio pratico della struttura della classe <xref:System.Runtime.Serialization.DataContractSerializer> sono prestazioni più avanzate, approssimativamente del dieci percento.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>  
  
-   <span data-ttu-id="d7bcd-130">Gli attributi da usare con la classe <xref:System.Xml.Serialization.XmlSerializer> non indicano quali campi o proprietà del tipo vengono serializzati in XML, mentre l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> da usare con la classe <xref:System.Runtime.Serialization.DataContractSerializer> mostra esplicitamente quali campi o proprietà vengono serializzati.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="d7bcd-131">I contratti dati sono quindi contratti espliciti sulla struttura dei dati che un'applicazione deve inviare e ricevere.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>  
  
-   <span data-ttu-id="d7bcd-132">La classe <xref:System.Xml.Serialization.XmlSerializer> può tradurre soltanto i membri pubblici di un oggetto .NET in XML, mentre la classe <xref:System.Runtime.Serialization.DataContractSerializer> può tradurre i membri di oggetti in XML indipendentemente dai modificatori di accesso di tali membri.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>  
  
-   <span data-ttu-id="d7bcd-133">Poiché è in grado di serializzare membri non pubblici di tipi in XML, la classe <xref:System.Runtime.Serialization.DataContractSerializer> ha meno restrizioni sulla varietà dei tipi .NET che può serializzare in XML.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="d7bcd-134">In particolare, questa classe può tradurre in XML tipi quali <xref:System.Collections.Hashtable> che implementano l'interfaccia <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="d7bcd-135">Con maggiore probabilità la classe <xref:System.Runtime.Serialization.DataContractSerializer> è in grado di serializzare in XML le istanze di qualsiasi tipo .NET preesistente senza dover modificare la definizione del tipo o sviluppare un wrapper specifico.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>  
  
-   <span data-ttu-id="d7bcd-136">Un'altra conseguenza della capacità della classe <xref:System.Runtime.Serialization.DataContractSerializer> di accedere ai membri non pubblici di un tipo è che richiede attendibilità totale, diversamente dalla classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="d7bcd-137">L'autorizzazione di accesso al codice di attendibilità totale fornisce l'accesso completo a tutte le risorse disponibili in un computer al quale è possibile accedere usando le credenziali usate per l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-137">The Full Trust code access permission give complete access to all resources on a machine that can be access using the credentials under which the code is executing.</span></span> <span data-ttu-id="d7bcd-138">Queste opzioni devono essere usate con attenzione in quanto il codice totalmente attendibile accede a tutte le risorse del computer.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-138">This options should be used with care as fully trusted code accesses all resources on your machine.</span></span>  
  
-   <span data-ttu-id="d7bcd-139">La classe <xref:System.Runtime.Serialization.DataContractSerializer> include alcune funzionalità di supporto per il controllo delle versioni:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>  
  
    -   <span data-ttu-id="d7bcd-140"><xref:System.Runtime.Serialization.DataMemberAttribute> ha una proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> alla quale può essere assegnato un valore false per i membri che vengono aggiunti a nuove versioni di un contratto dati che non erano presenti nelle versioni precedenti, consentendo così alle applicazioni con le nuove versioni del contratto di essere in grado di elaborare versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>  
  
    -   <span data-ttu-id="d7bcd-141">Se per un contratto dati viene implementata l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject>, è possibile consentire alla classe <xref:System.Runtime.Serialization.DataContractSerializer> di passare membri definiti in versioni più recenti di un contratto dati mediante applicazioni con versioni precedenti del contratto.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>  
  
 <span data-ttu-id="d7bcd-142">Nonostante tutte le differenze, il codice XML in cui la classe <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo per impostazione predefinita è semanticamente identico al codice XML in cui la classe <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, a condizione che lo spazio dei nomi per il codice XML sia definito esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="d7bcd-143">La classe seguente, che dispone di attributi per essere usata con entrambi i serializzatori, viene tradotta in codice XML semanticamente identico dalla classe <xref:System.Xml.Serialization.XmlSerializer> e dalla classe <xref:System.Runtime.Serialization.DataContractAttribute>:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-143">The following class, which has attributes for use with both of the serializers, are translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>  
  
```  
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
  
 <span data-ttu-id="d7bcd-144">Il software development kit (SDK) di Windows include uno strumento da riga di comando denominato il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Ad esempio lo strumento xsd.exe utilizzato con i servizi Web ASP.NET, Svcutil.exe può generare definizioni di tipi di dati .NET da XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="d7bcd-145">I tipi sono contratti dati se la classe <xref:System.Runtime.Serialization.DataContractSerializer> può generare codice XML nel formato definito dall'XML Schema. In caso contrario, sono destinati alla serializzazione mediante l'uso della classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-145">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d7bcd-146">Lo strumento Svcutil.exe può anche essere usato per generare schemi XML da contratti dati usando l'opzione `/dataContractOnly`.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-146">The tool, Svcutil.exe, can also be made to generate XML Schema from data contracts using its `/dataContractOnly` switch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7bcd-147">Sebbene i servizi Web ASP.NET utilizzino la classe <xref:System.Xml.Serialization.XmlSerializer> e la modalità di compatibilità ASP.NET di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fa sì che i servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] rispecchino il comportamento dei servizi Web ASP.NET, l'opzione di compatibilità ASP.NET non impedisce di usare la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-147">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode makes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d7bcd-148">È comunque possibile usare la classe <xref:System.Runtime.Serialization.DataContractSerializer> con servizi che sono in esecuzione nella modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-148">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="d7bcd-149">Sviluppo del servizio</span><span class="sxs-lookup"><span data-stu-id="d7bcd-149">Service Development</span></span>  
 <span data-ttu-id="d7bcd-150">Per sviluppare un servizio usando ASP.NET veniva in genere aggiunto l'attributo <xref:System.Web.Services.WebService> a una classe e l'attributo <xref:System.Web.Services.WebMethodAttribute> a uno dei metodi di tale classe che devono essere operazioni del servizio:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-150">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>  
  
```  
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
  
 <span data-ttu-id="d7bcd-151">ASP.NET 2.0 ha introdotto l'opzione di aggiunta dell'attributo <xref:System.Web.Services.WebService> e di <xref:System.Web.Services.WebMethodAttribute> a un'interfaccia piuttosto che a una classe e di scrittura di una classe per implementare l'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-151">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>  
  
```  
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
  
 <span data-ttu-id="d7bcd-152">È preferibile usare questa opzione in quanto l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare lo stesso contratto in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-152">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="d7bcd-153">Un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene fornito definendo uno o più endpoint [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-153">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is provided by defining one or more [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints.</span></span> <span data-ttu-id="d7bcd-154">Un endpoint è definito da un indirizzo, un binding e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-154">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="d7bcd-155">L'indirizzo definisce l'ubicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-155">The address defines where the service is located.</span></span> <span data-ttu-id="d7bcd-156">L'associazione specifica come comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-156">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="d7bcd-157">Il contratto di servizio definisce le operazioni che il servizio può eseguire.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-157">The service contract defines the operations that the service can perform.</span></span>  
  
 <span data-ttu-id="d7bcd-158">Il contratto di servizio viene in genere definito per primo, aggiungendo <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> a un'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-158">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>  
  
```  
[ServiceContract]  
public interface IEcho  
{  
     [OperationContract]  
     string Echo(string input);  
}  
```  
  
 <span data-ttu-id="d7bcd-159"><xref:System.ServiceModel.ServiceContractAttribute> specifica che l'interfaccia definisce un contratto di servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e <xref:System.ServiceModel.OperationContractAttribute> indica l'eventuale metodo dell'interfaccia che definisce operazioni del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-159">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>  
  
 <span data-ttu-id="d7bcd-160">Una volta che è stato definito, il contratto di servizio viene implementato in una classe, facendo in modo che la classe implementi l'interfaccia mediante la quale viene definito il contratto di servizio:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-160">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>  
  
```  
public class Service : IEcho  
{  
    public string Echo(string input)  
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="d7bcd-161">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] una classe che implementa un contratto di servizio è denominata tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-161">A class that implements a service contract is referred to as a service type in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="d7bcd-162">Il passaggio successivo consiste nell'associare un indirizzo e un'associazione a un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-162">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="d7bcd-163">Questa operazione viene in genere eseguita in un file di configurazione, modificando il file direttamente o usando un editor di configurazione fornito con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-163">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="d7bcd-164">Di seguito è riportato un esempio di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-164">Here is an example of a configuration file.</span></span>  
  
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
  
 <span data-ttu-id="d7bcd-165">L'associazione specifica il set di protocolli per la comunicazione con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-165">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="d7bcd-166">Nella tabella seguente sono elencate le associazioni fornite dal sistema che rappresentano opzioni comuni.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-166">The following table lists the system-provided bindings that represent common options.</span></span>  
  
|<span data-ttu-id="d7bcd-167">Nome</span><span class="sxs-lookup"><span data-stu-id="d7bcd-167">Name</span></span>|<span data-ttu-id="d7bcd-168">Scopo</span><span class="sxs-lookup"><span data-stu-id="d7bcd-168">Purpose</span></span>|  
|----------|-------------|  
|<span data-ttu-id="d7bcd-169">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-169">BasicHttpBinding</span></span>|<span data-ttu-id="d7bcd-170">Interoperabilità con servizi Web e client che supportano WS-BasicProfile 1.1 e Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-170">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|  
|<span data-ttu-id="d7bcd-171">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-171">WSHttpBinding</span></span>|<span data-ttu-id="d7bcd-172">Interoperabilità con servizi Web e client che supportano protocolli WS-* su HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-172">Interoperability with Web services and clients that support the WS-* protocols over HTTP.</span></span>|  
|<span data-ttu-id="d7bcd-173">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-173">WSDualHttpBinding</span></span>|<span data-ttu-id="d7bcd-174">Comunicazione HTTP duplex in base alla quale il ricevitore di un messaggio iniziale non risponde direttamente al mittente iniziale, ma può trasmettere un numero qualsiasi di risposte in un determinato periodo di tempo usando HTTP in conformità ai protocolli WS-*.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-174">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-* protocols.</span></span>|  
|<span data-ttu-id="d7bcd-175">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-175">WSFederationBinding</span></span>|<span data-ttu-id="d7bcd-176">Comunicazione HTTP nella quale l'accesso alle risorse di un servizio può essere controllato in base a credenziali rilasciate da un provider di credenziali identificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-176">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|  
|<span data-ttu-id="d7bcd-177">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-177">NetTcpBinding</span></span>|<span data-ttu-id="d7bcd-178">Comunicazione ad alte prestazioni protetta e affidabile tra entità software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] su una rete.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-178">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities across a network.</span></span>|  
|<span data-ttu-id="d7bcd-179">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-179">NetNamedPipeBinding</span></span>|<span data-ttu-id="d7bcd-180">Comunicazione ad alte prestazioni protetta e affidabile tra entità software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-180">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities on the same machine.</span></span>|  
|<span data-ttu-id="d7bcd-181">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-181">NetMsmqBinding</span></span>|<span data-ttu-id="d7bcd-182">Comunicazione tra entità software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante l'uso di MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-182">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using MSMQ.</span></span>|  
|<span data-ttu-id="d7bcd-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-183">MsmqIntegrationBinding</span></span>|<span data-ttu-id="d7bcd-184">Comunicazione tra un'entità software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e un'altra entità software mediante l'uso di MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-184">Communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entity and another software entity by using MSMQ.</span></span>|  
|<span data-ttu-id="d7bcd-185">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="d7bcd-185">NetPeerTcpBinding</span></span>|<span data-ttu-id="d7bcd-186">Comunicazione tra entità software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante l'uso di Windows Peer-to-Peer Networking.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-186">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using Windows Peer-to-Peer Networking.</span></span>|  
  
 <span data-ttu-id="d7bcd-187">L'associazione fornita dal sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora il set di protocolli supportato dai servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-187">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="d7bcd-188">Le associazioni personalizzate per le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono essere definite facilmente come raccolte delle classi dell'elemento di associazione usate da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per implementare singoli protocolli.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-188">Custom bindings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are easily defined as collections of the binding element classes that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses to implement individual protocols.</span></span> <span data-ttu-id="d7bcd-189">Nuovi elementi di associazione possono essere scritti per rappresentare protocolli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-189">New binding elements can be written to represent additional protocols.</span></span>  
  
 <span data-ttu-id="d7bcd-190">Il comportamento interno dei tipi di servizio può essere regolato usando le proprietà di una famiglia di classi denominate comportamenti.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-190">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="d7bcd-191">In questo caso la classe <xref:System.ServiceModel.ServiceBehaviorAttribute> viene usata per specificare che il tipo di servizio deve essere multithreading.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-191">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]  
public class DerivativesCalculatorServiceType: IDerivativesCalculator  
```  
  
 <span data-ttu-id="d7bcd-192">Alcuni comportamenti, come <xref:System.ServiceModel.ServiceBehaviorAttribute>, sono attributi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-192">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="d7bcd-193">I comportamenti con proprietà che gli amministratori vorrebbero impostare possono essere modificati nella configurazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-193">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>  
  
 <span data-ttu-id="d7bcd-194">Nella programmazione di tipi di servizio viene spesso usata la classe <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-194">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="d7bcd-195">La proprietà <xref:System.ServiceModel.OperationContext.Current%2A> statica di questa classe fornisce l'accesso a informazioni sul contesto nel quale viene eseguita un'operazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-195">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="d7bcd-196">L'oggetto <xref:System.ServiceModel.OperationContext> è simile a entrambe le classi <xref:System.Web.HttpContext> e <xref:System.EnterpriseServices.ContextUtil>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-196"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="d7bcd-197">Hosting</span><span class="sxs-lookup"><span data-stu-id="d7bcd-197">Hosting</span></span>  
 <span data-ttu-id="d7bcd-198">I servizi Web ASP.NET vengono compilati in un assembly della libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-198">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="d7bcd-199">Viene fornito un file denominato file del servizio che ha l'estensione asmx e contiene una direttiva `@ WebService` che identifica la classe che contiene il codice per il servizio e l'assembly in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-199">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>  
  
```  
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>  
```  
  
 <span data-ttu-id="d7bcd-200">Il file del servizio viene copiato in una radice dell'applicazione ASP.NET in Internet Information Services (IIS) e l'assembly viene copiato nella sottodirectory \bin di tale radice.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-200">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="d7bcd-201">Per accedere all'applicazione sarà quindi possibile usare l'URL (Uniform Resource Locator) del file del servizio nella radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-201">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>  
  
 <span data-ttu-id="d7bcd-202">I servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono essere ospitati immediatamente in IIS 5.1 o 6.0, il servizio di attivazione dei processi di Windows (WAS) fornito unitamente a IIS 7.0 e in qualsiasi applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-202">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="d7bcd-203">Per ospitare un servizio in IIS 5.1 o 6.0 il servizio deve usare HTTP come protocollo di trasporto delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-203">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>  
  
 <span data-ttu-id="d7bcd-204">Per ospitare un servizio in IIS 5.1, 6.0 o in WAS, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-204">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>  
  
1.  <span data-ttu-id="d7bcd-205">Compilare il tipo di servizio in un assembly della libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-205">Compile the service type into a class library assembly.</span></span>  
  
2.  <span data-ttu-id="d7bcd-206">Creare un file del servizio con un'estensione svc con una direttiva `@ ServiceHost` per identificare il tipo di servizio:</span><span class="sxs-lookup"><span data-stu-id="d7bcd-206">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>  
  
    ```  
    <%@ServiceHost language="c#" Service="MyService" %>  
    ```  
  
3.  <span data-ttu-id="d7bcd-207">Copiare il file del servizio in una directory virtuale e l'assembly nella sottodirectory \bin di tale directory.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-207">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>  
  
4.  <span data-ttu-id="d7bcd-208">Copiare il file di configurazione nella directory virtuale e denominarlo Web.config.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-208">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>  
  
 <span data-ttu-id="d7bcd-209">Per accedere all'applicazione sarà quindi possibile usare l'URL del file del servizio nella radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-209">The application is then accessible by using the URL of the service file in the application root.</span></span>  
  
 <span data-ttu-id="d7bcd-210">Per ospitare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all'interno di un'applicazione .NET, compilare il tipo di servizio in un assembly della libreria di classi a cui fa riferimento l'applicazione e programmare l'applicazione affinché ospiti il servizio usando la classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-210">To host a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="d7bcd-211">Di seguito è riportato un esempio della programmazione di base necessaria.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-211">The following is an example of the basic programming required:</span></span>  
  
```  
string httpBaseAddress = "http://www.contoso.com:8000/";  
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";  
  
Uri httpBaseAddressUri = new Uri(httpBaseAddress);  
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);  
  
Uri[] baseAdresses = new Uri[] {   
 httpBaseAddressUri,  
 tcpBaseAddressUri};  
  
using(ServiceHost host = new ServiceHost(  
typeof(Service), //"Service" is the name of the service type baseAdresses))  
{  
     host.Open();  
  
     […] //Wait to receive messages  
     host.Close();  
}  
```  
  
 <span data-ttu-id="d7bcd-212">Questo esempio mostra in che modo vengono specificati gli indirizzi per uno o più protocolli di trasporto nella costruzione di una classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-212">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d7bcd-213">Questi indirizzi sono detti indirizzi di base.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-213">These addresses are referred to as base addresses.</span></span>  
  
 <span data-ttu-id="d7bcd-214">L'indirizzo fornito per un endpoint di un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è un indirizzo relativo di un indirizzo di base dell'host dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-214">The address provided for any endpoint of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="d7bcd-215">L'host può avere un indirizzo di base per ogni protocollo di trasporto della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-215">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="d7bcd-216">Nella configurazione di esempio nel file di configurazione precedente, il costruttore <xref:System.ServiceModel.BasicHttpBinding> selezionato per l'endpoint usa HTTP come protocollo di trasporto. L'indirizzo dell'endpoint, `EchoService` è quindi relativo all'indirizzo di base HTTP dell'host.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-216">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="d7bcd-217">Nel caso dell'host dell'esempio precedente, l'indirizzo di base HTTP è http://www.contoso.com: 8000/.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-217">In the case of the host in the preceding example, the HTTP base address is http://www.contoso.com:8000/.</span></span> <span data-ttu-id="d7bcd-218">Nel caso di un servizio ospitato in IIS o WAS, l'indirizzo di base è l'URL del file del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-218">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>  
  
 <span data-ttu-id="d7bcd-219">Soltanto ai servizi ospitati in IIS o WAS e che sono configurati in modo esclusivo con HTTP come protocollo di trasporto può essere consentito di usare l'opzione della modalità di compatibilità ASP.NET di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-219">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode option.</span></span> <span data-ttu-id="d7bcd-220">Per attivare questa opzione è necessario eseguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-220">Turning that option on requires the following steps.</span></span>  
  
1.  <span data-ttu-id="d7bcd-221">Il programmatore deve aggiungere l'attributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo di servizio e deve specificare che la modalità di compatibilità ASP.NET è consentita o necessaria.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-221">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>  
  
    ```  
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(  
          RequirementsMode=AspNetCompatbilityRequirementsMode.Require)]  
    public class DerivativesCalculatorServiceType: IDerivativesCalculator  
    ```  
  
2.  <span data-ttu-id="d7bcd-222">L'amministratore deve configurare l'applicazione per l'uso della modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-222">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>  
  
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
  
     <span data-ttu-id="d7bcd-223">Le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono essere configurate anche per usare asmx, anziché l'estensione svc, come estensione per i relativi file di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>  
  
    ```xml  
    <system.web>  
         <compilation>  
          <compilation debug="true">  
          <buildProviders>  
           <remove extension=".asmx"/>  
           <add extension=".asmx"   
            type="System.ServiceModel.ServiceBuildProvider,   
            Systemm.ServiceModel,   
            Version=3.0.0.0,   
            Culture=neutral,   
            PublicKeyToken=b77a5c561934e089" />  
          </buildProviders>  
          </compilation>  
         </compilation>  
    </system.web>  
    ```  
  
     <span data-ttu-id="d7bcd-224">Questa opzione può evitare la necessità di modificare i client configurati per l'uso degli URL dei file di servizio con estensione asmx quando si modifica un servizio per l'uso di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-224">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="client-development"></a><span data-ttu-id="d7bcd-225">Sviluppo client</span><span class="sxs-lookup"><span data-stu-id="d7bcd-225">Client Development</span></span>  
 <span data-ttu-id="d7bcd-226">I client per i servizi Web ASP.NET vengono generati usando lo strumento da riga di comando WSDL.exe che fornisce come input l'URL del file con estensione asmx.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-226">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="d7bcd-227">Lo strumento corrispondente, fornito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d7bcd-227">The corresponding tool provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="d7bcd-228">Genera un modulo di codice con la definizione del contratto di servizio e la definizione di una classe client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-228">It generates a code module with the definition of the service contract and the definition of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class.</span></span> <span data-ttu-id="d7bcd-229">Genera anche un file di configurazione con l'indirizzo e l'associazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-229">It also generates a configuration file with the address and binding of the service.</span></span>  
  
 <span data-ttu-id="d7bcd-230">Per programmare un client per un servizio remoto è in genere consigliabile eseguire la programmazione in base a un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-230">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="d7bcd-231">Il codice generato dallo strumento WSDL.exe fornisce sempre per entrambi un modello sincrono e un modello asincrono per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-231">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="d7bcd-232">Il codice generato dal [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può fornire per un modello.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-232">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="d7bcd-233">Per impostazione predefinita viene usato per il modello sincrono.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-233">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="d7bcd-234">Se lo strumento viene eseguito con l'opzione `/async`, il codice generato viene usato per il modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-234">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>  
  
 <span data-ttu-id="d7bcd-235">Non esiste alcuna garanzia che i nomi inclusi nelle classi client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generate dallo strumento WSDL.exe di ASP.NET corrispondano per impostazione predefinita ai nomi inclusi nelle classi client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generate dallo strumento Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-235">There is no guarantee that names in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="d7bcd-236">In particolare, nel codice generato dallo strumento Svcutil.exe ai nomi delle proprietà di classi che devono essere serializzate usando la classe <xref:System.Xml.Serialization.XmlSerializer> viene assegnato, per impostazione predefinita, il suffisso Property. Questo non accade invece nel codice generato dallo strumento WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-236">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>  
  
## <a name="message-representation"></a><span data-ttu-id="d7bcd-237">Rappresentazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d7bcd-237">Message Representation</span></span>  
 <span data-ttu-id="d7bcd-238">Le intestazioni dei messaggi SOAP inviati e ricevuti dai servizi Web ASP.NET possono essere personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-238">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="d7bcd-239">Una classe viene derivata dalla classe <xref:System.Web.Services.Protocols.SoapHeader> per definire la struttura dell'intestazione. La classe <xref:System.Web.Services.Protocols.SoapHeaderAttribute> viene quindi usata per indicare la presenza dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-239">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>  
  
```  
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
  
 <span data-ttu-id="d7bcd-240">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce gli attributi, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute> per descrivere la struttura dei messaggi SOAP inviati e ricevuti da un servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-240">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>  
  
```  
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
public class ItemMesage  
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
  
 <span data-ttu-id="d7bcd-241">Questa sintassi genera una rappresentazione esplicita della struttura dei messaggi, mentre la struttura dei messaggi è implicita nel codice di un servizio Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-241">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="d7bcd-242">Inoltre, nella sintassi ASP.NET le intestazioni dei messaggi sono rappresentate come proprietà del servizio, come la proprietà `ProtocolHeader` nell'esempio precedente, mentre nella sintassi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono rappresentate più appropriatamente come proprietà dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-242">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="d7bcd-243">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le intestazioni dei messaggi possono inoltre essere aggiunte alla configurazione di endpoint.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-243">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows message headers to be added to the configuration of endpoints.</span></span>  
  
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
  
 <span data-ttu-id="d7bcd-244">Questa opzione consente di evitare qualsiasi riferimento a intestazioni di protocollo infrastrutturali nel codice per un client o un servizio: le intestazioni vengono aggiunte ai messaggi a seconda della modalità di configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-244">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>  
  
## <a name="service-description"></a><span data-ttu-id="d7bcd-245">Descrizione del servizio</span><span class="sxs-lookup"><span data-stu-id="d7bcd-245">Service Description</span></span>  
 <span data-ttu-id="d7bcd-246">La pubblicazione di una richiesta HTTP GET per il file asmx di un servizio Web ASP.NET con la query WSDL determina in ASP.NET la generazione del file WSDL per descrivere il servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-246">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="d7bcd-247">Il file WSDL viene restituito da ASP.NET come risposta alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-247">It returns that WSDL as the response to the request.</span></span>  
  
 <span data-ttu-id="d7bcd-248">ASP.NET 2.0 consente di verificare che un servizio sia conforme alla specifica Basic Profile 1.1 di WS-I (Web Services-Interoperability Organization ) e di inserire un'attestazione di conformità del servizio nel relativo file WSDL.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-248">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="d7bcd-249">Questa verifica viene effettuata usando i parametri `ConformsTo` e `EmitConformanceClaims` dell'attributo <xref:System.Web.Services.WebServiceBindingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-249">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="d7bcd-250">Il WSDL generato da ASP.NET per un servizio può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-250">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="d7bcd-251">Le personalizzazioni vengono effettuate creando una classe derivata di <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> per aggiungere elementi al WSDL.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-251">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>  
  
 <span data-ttu-id="d7bcd-252">L'invio di una richiesta HTTP GET con la query WSDL per il file svc di un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con un endpoint HTTP ospitato in IIS 5.1, 6.0 o WAS determina una risposta di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con WSDL per descrivere il servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-252">Issuing an HTTP GET request with the query WSDL for the .svc file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to respond with WSDL to describe the service.</span></span> <span data-ttu-id="d7bcd-253">L'invio di una richiesta GET HTTP con la query WSDL all'indirizzo di base HTTP di un servizio ospitato in un'applicazione .NET produce lo stesso effetto di quando httpGetEnabled è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-253">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>  
  
 <span data-ttu-id="d7bcd-254">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde tuttavia anche a richieste WS-MetadataExchange con il WSDL che genera per descrivere un servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-254">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="d7bcd-255">I servizi Web ASP.NET non dispongono di supporto incorporato per le richieste WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-255">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>  
  
 <span data-ttu-id="d7bcd-256">Il WSDL generato da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può essere ampiamente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-256">The WSDL that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates can be extensively customized.</span></span> <span data-ttu-id="d7bcd-257">La classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> fornisce alcune funzioni per la personalizzazione di WSDL.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-257">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="d7bcd-258">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può anche essere configurato per evitare la generazione di WSDL e usare invece un file WSDL statico in un determinato URL.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>  
  
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
  
## <a name="exception-handling"></a><span data-ttu-id="d7bcd-259">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="d7bcd-259">Exception Handling</span></span>  
 <span data-ttu-id="d7bcd-260">Nei servizi Web ASP.NET le eccezioni non gestite vengono restituite ai client come errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-260">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="d7bcd-261">È anche possibile generare esplicitamente istanze della classe <xref:System.Web.Services.Protocols.SoapException> e disporre di maggiore controllo sul contenuto dell'errore SOAP che viene trasmesso al client.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-261">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>  
  
 <span data-ttu-id="d7bcd-262">Nei servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le eccezioni non gestite non vengono restituite ai client come errori SOAP per evitare che informazioni riservate vengano esposte accidentalmente attraverso le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-262">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="d7bcd-263">Viene fornita un'impostazione di configurazione per fare in modo che le eccezioni non gestite vengano restituite ai client a scopo di debug.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-263">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>  
  
 <span data-ttu-id="d7bcd-264">Per restituire gli errori SOAP ai client è possibile generare istanze del tipo generico, <xref:System.ServiceModel.FaultException%601>, usando il tipo di contratto dati come tipo generico.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-264">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="d7bcd-265">È anche possibile aggiungere attributi <xref:System.ServiceModel.FaultContractAttribute> alle operazioni per specificare gli errori che un'operazione potrebbe generare.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-265">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>  
  
```  
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
  
 <span data-ttu-id="d7bcd-266">In questo modo i potenziali errori vengono annunciati nel WSDL per il servizio, consentendo ai programmatori dei client di prevedere quali errori potrebbero risultare da un'operazione e di scrivere le istruzioni Catch appropriate.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-266">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>  
  
```  
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
  
## <a name="state-management"></a><span data-ttu-id="d7bcd-267">Gestione dello stato</span><span class="sxs-lookup"><span data-stu-id="d7bcd-267">State Management</span></span>  
 <span data-ttu-id="d7bcd-268">La classe usata per implementare un servizio Web ASP.NET può essere derivata da <xref:System.Web.Services.WebService>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-268">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>  
  
```  
public class Service : WebService, IEcho  
{  
  
 public string Echo(string input)  
 {  
  return input;  
 }  
}  
```  
  
 <span data-ttu-id="d7bcd-269">In tal caso, la classe può essere programmata per usare la proprietà Context della classe di base <xref:System.Web.Services.WebService> per accedere a un oggetto <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-269">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="d7bcd-270">L'oggetto <xref:System.Web.HttpContext> può essere usato per aggiornare e recuperare informazioni sullo stato dell'applicazione usando la relativa proprietà Application, nonché per aggiornare e recuperare informazioni sullo stato della sessione usando la relativa proprietà Session.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-270">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>  
  
 <span data-ttu-id="d7bcd-271">ASP.NET fornisce un livello di controllo elevato sulla posizione in cui vengono effettivamente memorizzate le informazioni sullo stato della sessione alla quali è possibile accedere usando la proprietà Session dell'oggetto <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-271">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="d7bcd-272">Possono essere memorizzate in cookie, in un database, nella memoria del server corrente o nella memoria di un server specificato.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-272">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="d7bcd-273">La scelta viene effettuata nel file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-273">The choice is made in the service’s configuration file.</span></span>  
  
 <span data-ttu-id="d7bcd-274">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce oggetti estensibili per la gestione dello stato.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides extensible objects for state management.</span></span> <span data-ttu-id="d7bcd-275">Gli oggetti estensibili sono oggetti che implementano l'interfaccia <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-275">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="d7bcd-276">Gli oggetti estendibili più importanti sono <xref:System.ServiceModel.ServiceHostBase> e <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-276">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="d7bcd-277">`ServiceHostBase` consente di mantenere lo stato al quale possono accedere tutte le istanze di tutti i tipi di servizio sullo stesso host, mentre `InstanceContext` consente di mantenere lo stato al quale può accedere qualsiasi codice in esecuzione nella stessa istanza di un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-277">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>  
  
 <span data-ttu-id="d7bcd-278">In questo caso, il tipo di servizio `TradingSystem` ha una classe <xref:System.ServiceModel.ServiceBehaviorAttribute> che specifica che tutte le chiamate dalla stessa istanza client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]vengano indirizzate alla stessa istanza del tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-278">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client instance are routed to the same instance of the service type.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class TradingSystem: ITradingService  
```  
  
 <span data-ttu-id="d7bcd-279">La classe `DealData` definisce lo stato al quale può accedere qualsiasi codice in esecuzione nella stessa istanza di un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-279">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>  
  
```  
internal class DealData: IExtension<InstanceContext>  
{  
 public string DealIdentifier = null;  
 public Trade[] Trades = null;  
}  
```  
  
 <span data-ttu-id="d7bcd-280">Nel codice del tipo di servizio che implementa una delle operazioni del contratto di servizio viene aggiunto un oggetto stato `DealData` allo stato dell'istanza corrente del tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-280">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>  
  
```  
string ITradingService.BeginDeal()  
{  
 string dealIdentifier = Guid.NewGuid().ToString();  
 DealData state = new DealData(dealIdentifier);  
 OperationContext.Current.InstanceContext.Extensions.Add(state);  
 return dealIdentifier;  
}  
```  
  
 <span data-ttu-id="d7bcd-281">Questo oggetto stato può essere successivamente recuperato e modificato dal codice che implementa un'altra delle operazioni del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-281">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>  
  
```  
void ITradingService.AddTrade(Trade trade)  
{  
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();  
 dealData.AddTrade(trade);  
}  
```  
  
 <span data-ttu-id="d7bcd-282">Mentre ASP.NET fornisce il controllo sulla posizione in cui vengono effettivamente memorizzate le informazioni sullo stato nella classe <xref:System.Web.HttpContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], almeno nella versione iniziale, non fornisce alcun controllo sulla posizione di memorizzazione degli oggetti estensibili.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-282">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="d7bcd-283">È principalmente questo aspetto che giustifica la selezione della modalità di compatibilità ASP.NET per un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-283">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="d7bcd-284">Se la gestione dello stato configurabile è imperativa, la scelta della modalità di compatibilità ASP.NET consente di usare le funzioni della classe <xref:System.Web.HttpContext> esattamente nel modo in cui vengono usate in ASP.NET, nonché di configurare la posizione in cui vengono memorizzate le informazioni sullo stato gestite mediante la classe <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-284">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>  
  
## <a name="security"></a><span data-ttu-id="d7bcd-285">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7bcd-285">Security</span></span>  
 <span data-ttu-id="d7bcd-286">Le opzioni per la protezione dei servizi Web ASP.NET sono le stesse usate per la protezione di qualsiasi applicazione IIS.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-286">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="d7bcd-287">Poiché le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono essere ospitate non solo in IIS, ma anche in qualsiasi file eseguibile .NET, le opzioni per la protezione delle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] devono essere rese indipendenti dalle funzioni di IIS.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-287">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can be hosted not only within IIS but also within any .NET executable, the options for securing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="d7bcd-288">Le funzioni fornite per i servizi Web ASP.NET sono tuttavia disponibili anche per i servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in esecuzione in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-288">However, the facilities provided for ASP.NET Web services are also available for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-authentication"></a><span data-ttu-id="d7bcd-289">Protezione: autenticazione</span><span class="sxs-lookup"><span data-stu-id="d7bcd-289">Security: Authentication</span></span>  
 <span data-ttu-id="d7bcd-290">IIS fornisce funzionalità per il controllo di accesso alle applicazioni tra le quali è possibile selezionare l'accesso anonimo o varie modalità di autenticazione: autenticazione di Windows, autenticazione digest, autenticazione di base e autenticazione .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-290">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="d7bcd-291">L'opzione Autenticazione di Windows può essere usata per controllare l'accesso ai servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-291">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="d7bcd-292">Tuttavia, quando un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è ospitata in IIS, quest'ultimo deve essere configurato per permettere l'accesso anonimo all'applicazione, in modo tale che l'autenticazione possa essere gestita da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stesso. WCF supporta infatti, tra le varie altre opzioni, l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-292">However, when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="d7bcd-293">Le altre opzioni incorporate includono token del nome utente, certificati X.509, token SAML e schede CardSpace, ma è comunque possibile definire meccanismi di autenticazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-293">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>  
  
### <a name="security-impersonation"></a><span data-ttu-id="d7bcd-294">Protezione: rappresentazione</span><span class="sxs-lookup"><span data-stu-id="d7bcd-294">Security: Impersonation</span></span>  
 <span data-ttu-id="d7bcd-295">ASP.NET fornisce un elemento di identità mediante il quale un servizio Web ASP.NET può essere impostato per rappresentare un determinato utente o le credenziali utente che vengono fornite con la richiesta corrente.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-295">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="d7bcd-296">Questo elemento può essere usato per configurare la rappresentazione in applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in esecuzione in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-296">That element can be used to configure impersonation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications running in ASP.NET compatibility mode.</span></span>  
  
 <span data-ttu-id="d7bcd-297">Il sistema di configurazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce un proprio elemento di identità per la definizione di un determinato utente da rappresentare.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="d7bcd-298">I client e i servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono inoltre essere configurati indipendentemente per la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-298">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="d7bcd-299">I client possono essere configurati per rappresentare l'utente corrente quando trasmettono richieste.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-299">Clients can be configured to impersonate the current user when they transmit requests.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DerivativesCalculatorClientBehavior">  
      <clientCredentials>  
      <windows allowedImpersonationLevel="Impersonation"/>  
      </clientCredentials>  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="d7bcd-300">Le operazioni dei servizi possono essere configurate per rappresentare le credenziali utente fornite con la richiesta corrente.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-300">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public void Receive(Message input)  
```  
  
### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="d7bcd-301">Protezione: autorizzazione mediante elenchi di controllo di accesso (ACL)</span><span class="sxs-lookup"><span data-stu-id="d7bcd-301">Security: Authorization using Access Control Lists</span></span>  
 <span data-ttu-id="d7bcd-302">Gli elenchi di controllo di accesso (ACL) possono essere usati per limitare l'accesso ai file con estensione asmx.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-302">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="d7bcd-303">Gli ACL nei file con estensione svc di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono ignorati, eccetto nella modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-303">However, ACLs on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .svc files are ignored except in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-role-based-authorization"></a><span data-ttu-id="d7bcd-304">Protezione: autorizzazione basata sui ruoli</span><span class="sxs-lookup"><span data-stu-id="d7bcd-304">Security: Role-based Authorization</span></span>  
 <span data-ttu-id="d7bcd-305">L'opzione Autenticazione di Windows di IIS può essere usata insieme all'elemento di autorizzazione fornito dal linguaggio di configurazione di ASP.NET per facilitare l'autorizzazione basata sui ruoli per i servizi Web ASP.NET basati sui gruppi di Windows ai quali sono assegnati gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-305">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="d7bcd-306">ASP.NET 2.0 ha introdotto un meccanismo più generale di autorizzazione basata sui ruoli: i provider di ruoli.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-306">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>  
  
 <span data-ttu-id="d7bcd-307">I provider di ruoli sono classi che implementano tutte un'interfaccia di base per ottenere informazioni sui ruoli ai quali è assegnato un utente, ma ogni provider di ruoli sa come recuperare tali informazioni da un'origine diversa.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-307">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="d7bcd-308">ASP.NET 2.0 fornisce un provider di ruoli in grado di recuperare assegnazioni di ruolo da un database Microsoft SQL Server e un altro provider in grado di recuperare assegnazioni di ruolo da Gestione autorizzazioni di Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-308">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>  
  
 <span data-ttu-id="d7bcd-309">Il meccanismo del provider di ruoli può essere usato indipendentemente da ASP.NET in qualsiasi applicazione .NET, incluse le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7bcd-309">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="d7bcd-310">La configurazione di esempio seguente per un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mostra come l'uso di un provider di ruoli ASP.NET sia un'opzione selezionata mediante la classe <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-310">The following sample configuration for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
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
  
### <a name="security-claims-based-authorization"></a><span data-ttu-id="d7bcd-311">Protezione: autorizzazione basata sulle attestazioni</span><span class="sxs-lookup"><span data-stu-id="d7bcd-311">Security: Claims-based Authorization</span></span>  
 <span data-ttu-id="d7bcd-312">Una delle più importanti innovazioni di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è il supporto per l'autorizzazione dell'accesso a risorse protette basata sulle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-312">One of the most important innovations of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="d7bcd-313">Le attestazioni sono costituite da un tipo, da un diritto e da un valore, ad esempio la licenza di un driver.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-313">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="d7bcd-314">In questo caso WCF crea un set di attestazioni relative al titolare della licenza, una delle quali è la data di nascita del titolare.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-314">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="d7bcd-315">Il tipo di questa attestazione è data di nascita, mentre il valore dell'attestazione è la data di nascita del titolare della licenza.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-315">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="d7bcd-316">Il diritto che un'attestazione conferisce al titolare specifica le operazioni che possono essere eseguite dal titolare con il valore dell'attestazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-316">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="d7bcd-317">Nel caso dell'attestazione della data di nascita del titolare della licenza, il diritto è possesso: il titolare possiede quella data di nascita ma non può, ad esempio, modificarla.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-317">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="d7bcd-318">L'autorizzazione basata sulle attestazioni include l'autorizzazione basata sui ruoli in quanto i ruoli sono un tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-318">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>  
  
 <span data-ttu-id="d7bcd-319">L'autorizzazione basata sulle attestazioni viene eseguita confrontando un set di attestazioni ai requisiti di accesso dell'operazione e, a seconda del risultato di tale confronto, concedendo o negando l'accesso all'operazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-319">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="d7bcd-320">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è possibile specificare una classe da usare per eseguire l'autorizzazione basata sulle attestazioni, anche in questo caso assegnando un valore alla proprietà `ServiceAuthorizationManager` della classe <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-320">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<behaviors>  
     <behavior name='ServiceBehavior'>  
     <serviceAuthorization   
     serviceAuthorizationManagerType=  
                   'Service.AccessChecker, Service' />  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="d7bcd-321">Le classi usate per eseguire l'autorizzazione basata sulle attestazioni devono derivare da <xref:System.ServiceModel.ServiceAuthorizationManager>, che deve eseguire l'override di un solo metodo, `AccessCheck()`.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-321">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d7bcd-322"> chiama questo metodo ogni volta che viene richiamata un'operazione del servizio e fornisce un oggetto <xref:System.ServiceModel.OperationContext> che dispone delle attestazioni per l'utente nella relativa proprietà `ServiceSecurityContext.AuthorizationContext`.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-322"> calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d7bcd-323"> raggruppa le attestazioni relative all'utente da qualsiasi token di sicurezza fornito dall'utente per l'autenticazione, evitando così la necessità di valutare se tali attestazioni sono sufficienti per le operazioni in questione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-323"> does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>  
  
 <span data-ttu-id="d7bcd-324">Il fatto che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assembli automaticamente le attestazioni provenienti da qualsiasi tipo di token di sicurezza rappresenta un'innovazione estremamente significativa in quanto il codice basato sulle attestazioni viene reso totalmente indipendente dal meccanismo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-324">That [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="d7bcd-325">L'autorizzazione mediante ACL e l'autorizzazione basata sui ruoli in ASP.NET sono invece strettamente collegate all'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-325">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>  
  
### <a name="security-confidentiality"></a><span data-ttu-id="d7bcd-326">Protezione: riservatezza</span><span class="sxs-lookup"><span data-stu-id="d7bcd-326">Security: Confidentiality</span></span>  
 <span data-ttu-id="d7bcd-327">La riservatezza dei messaggi scambiati con servizi Web ASP.NET può essere garantita al livello del trasporto configurando l'applicazione in IIS per l'uso del protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-327">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="d7bcd-328">Lo stesso può essere fatto per le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitate in IIS.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-328">The same can be done for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted within IIS.</span></span> <span data-ttu-id="d7bcd-329">Le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitate al di fuori di IIS possono essere configurate anche per l'uso di un protocollo di trasporto sicuro.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-329">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="d7bcd-330">In aggiunta, le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono essere configurate anche per proteggere i messaggi prima che vengano trasportati usando il protocollo WS-Security.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-330">More important, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="d7bcd-331">La protezione del solo corpo del messaggio mediante il protocollo WS-Security consente la trasmissione riservata del messaggio su intermediari prima di raggiungere la destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-331">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>  
  
## <a name="globalization"></a><span data-ttu-id="d7bcd-332">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="d7bcd-332">Globalization</span></span>  
 <span data-ttu-id="d7bcd-333">Il linguaggio di configurazione di ASP.NET consente di specificare le impostazioni cultura per i singoli servizi.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-333">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="d7bcd-334">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non supporta questa impostazione di configurazione, eccetto in modalità di compatibilità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-334">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="d7bcd-335">Per individuare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che non usa la modalità compatibilità ASP.NET, compilare il tipo di servizio in assembly specifici delle impostazioni cultura e disporre endpoint specifici per ogni assembly specifico delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="d7bcd-335">To localize a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7bcd-336">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7bcd-336">See Also</span></span>  
 [<span data-ttu-id="d7bcd-337">Confronto tra servizi Web ASP.NET e WCF basato sullo scopo e gli standard utilizzati</span><span class="sxs-lookup"><span data-stu-id="d7bcd-337">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
