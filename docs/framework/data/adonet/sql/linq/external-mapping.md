---
title: Mapping esterno
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: ba5af75ae34b233354fec6e9074f3cc96d924c7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003053"
---
# <a name="external-mapping"></a><span data-ttu-id="6d6be-102">Mapping esterno</span><span class="sxs-lookup"><span data-stu-id="6d6be-102">External Mapping</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6d6be-103">supporta il *mapping esterno*, un processo mediante il quale si utilizza un file XML separato per specificare il mapping tra il modello di dati del database e il modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="6d6be-103">supports *external mapping*, a process by which you use a separate XML file to specify mapping between the data model of the database and your object model.</span></span> <span data-ttu-id="6d6be-104">I vantaggi dell'uso di un file di mapping esterno sono:</span><span class="sxs-lookup"><span data-stu-id="6d6be-104">Advantages of using an external mapping file include the following:</span></span>  
  
- <span data-ttu-id="6d6be-105">È possibile evitare di includere il codice di mapping nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d6be-105">You can keep your mapping code out of your application code.</span></span> <span data-ttu-id="6d6be-106">Questo approccio evita confusione nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d6be-106">This approach reduces clutter in your application code.</span></span>  
  
- <span data-ttu-id="6d6be-107">Un file di mapping esterno è simile a un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6d6be-107">You can treat an external mapping file something like a configuration file.</span></span> <span data-ttu-id="6d6be-108">Ad esempio, è possibile aggiornare il modo in cui l'applicazione si comporta dopo avere fornito i file binari semplicemente eseguendo lo swapping del file di mapping esterno.</span><span class="sxs-lookup"><span data-stu-id="6d6be-108">For example, you can update how your application behaves after shipping the binaries by just swapping out the external mapping file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6be-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d6be-109">Requirements</span></span>  
 <span data-ttu-id="6d6be-110">Il file di mapping deve essere un file XML e il file deve essere convalidato in base a un file di definizione dello schema [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (XSD).</span><span class="sxs-lookup"><span data-stu-id="6d6be-110">The mapping file must be an XML file, and the file must validate against a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] schema definition (.xsd) file.</span></span>  
  
 <span data-ttu-id="6d6be-111">È necessario attenersi alle regole che seguono:</span><span class="sxs-lookup"><span data-stu-id="6d6be-111">The following rules apply:</span></span>  
  
- <span data-ttu-id="6d6be-112">Il file di mapping deve essere un file XML.</span><span class="sxs-lookup"><span data-stu-id="6d6be-112">The mapping file must be an XML file.</span></span>  
  
- <span data-ttu-id="6d6be-113">Il file di mapping XML deve essere convalidato in base al file di definizione di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="6d6be-113">The XML mapping file must be valid against the XML schema definition file.</span></span> <span data-ttu-id="6d6be-114">Per altre informazioni, vedere [Procedura: Convalidare file di mapping esterni e DBML @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="6d6be-114">For more information, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
- <span data-ttu-id="6d6be-115">Il mapping esterno esegue l'override del mapping basato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="6d6be-115">External mapping overrides attribute-based mapping.</span></span> <span data-ttu-id="6d6be-116">In altre parole, quando si usa un'origine del mapping esterna per creare un oggetto <xref:System.Data.Linq.DataContext>, <xref:System.Data.Linq.DataContext> ignora tutti gli attributi di mapping creati nelle classi.</span><span class="sxs-lookup"><span data-stu-id="6d6be-116">In other words, when you use an external mapping source to create a <xref:System.Data.Linq.DataContext>, the <xref:System.Data.Linq.DataContext> ignores all mapping attributes you have created on classes.</span></span> <span data-ttu-id="6d6be-117">Questo comportamento si verifica se la classe è inclusa nel file di mapping esterno.</span><span class="sxs-lookup"><span data-stu-id="6d6be-117">This behavior is true whether the class is included in the external mapping file.</span></span>  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6d6be-118">non supporta l'uso ibrido dei due approcci del mapping (esterno e basato sugli attributi).</span><span class="sxs-lookup"><span data-stu-id="6d6be-118">does not support the hybrid use of the two mapping approaches (attribute-based and external).</span></span>  
  
## <a name="xml-schema-definition-file"></a><span data-ttu-id="6d6be-119">File di definizione di XML Schema</span><span class="sxs-lookup"><span data-stu-id="6d6be-119">XML Schema Definition File</span></span>  
 <span data-ttu-id="6d6be-120">Il mapping esterno in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deve essere convalidato in base alla seguente definizione di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="6d6be-120">External mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be valid against the following XML schema definition.</span></span>  
  
 <span data-ttu-id="6d6be-121">È necessario distinguere questo file di definizione dello schema dal file di definizione dello schema usato per convalidare un file DBML.</span><span class="sxs-lookup"><span data-stu-id="6d6be-121">Distinguish this schema definition file from the schema definition file that is used to validate a DBML file.</span></span> <span data-ttu-id="6d6be-122">Per ulteriori informazioni, vedere [generazione di codice in LINQ to SQL](code-generation-in-linq-to-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="6d6be-122">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d6be-123">Gli utenti di Visual Studio troveranno inoltre questo file XSD nella finestra di dialogo XML Schema come "LinqToSqlMapping. xsd".</span><span class="sxs-lookup"><span data-stu-id="6d6be-123">Visual Studio users will also find this XSD file in the XML Schemas dialog box as "LinqToSqlMapping.xsd".</span></span> <span data-ttu-id="6d6be-124">Per usare questo file correttamente per la convalida di un file di mapping esterno, vedere [How per: Convalidare file di mapping esterni e DBML @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="6d6be-124">To use this file correctly for validating an external mapping file, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d6be-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d6be-125">See also</span></span>

- [<span data-ttu-id="6d6be-126">Generazione di codice in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6d6be-126">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="6d6be-127">Riferimento</span><span class="sxs-lookup"><span data-stu-id="6d6be-127">Reference</span></span>](reference.md)
- <span data-ttu-id="6d6be-128">[Procedura: Generare il modello a oggetti come file esterno @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="6d6be-128">[How to: Generate the Object Model as an External File](how-to-generate-the-object-model-as-an-external-file.md)</span></span>
