---
title: Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 231f23ccf47f60b902fdd5c66b63fe1a750445f9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203410"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="a1dc2-102">Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="a1dc2-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="a1dc2-103">In uno schema XSD (XML Schema Definition Language), l'elemento **Unique** specifica il vincolo di univocità per un elemento o un attributo.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="a1dc2-104">Durante il processo di conversione di un XML Schema in uno schema relazionale, viene eseguito il mapping del vincolo univoco specificato su un elemento o un attributo dell'XML Schema a un vincolo univoco del tipo <xref:System.Data.DataTable> nel tipo <xref:System.Data.DataSet> corrispondente generato.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="a1dc2-105">Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **Unique** .</span><span class="sxs-lookup"><span data-stu-id="a1dc2-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="a1dc2-106">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="a1dc2-106">Attribute name</span></span>|<span data-ttu-id="a1dc2-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a1dc2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a1dc2-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="a1dc2-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="a1dc2-109">Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="a1dc2-110">In caso contrario, l'attributo **Name** fornisce il valore del nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="a1dc2-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="a1dc2-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="a1dc2-112">Se `PrimaryKey="true"` è presente nell'elemento **Unique** , viene creato un vincolo unique con la proprietà **IsPrimaryKey** impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="a1dc2-113">Nell'esempio seguente viene illustrato un XML Schema che utilizza l'elemento **Unique** per specificare un vincolo di univocità.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="a1dc2-114">L'elemento **Unique** nello schema specifica che per tutti gli elementi **Customers** in un'istanza del documento, il valore dell'elemento figlio **CustomerID** deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="a1dc2-115">Durante la compilazione del **set di dati**, il processo di mapping legge questo schema e genera la tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a1dc2-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="a1dc2-116">Il processo di mapping crea anche un vincolo UNIQUE nella colonna **CustomerID** , come illustrato nel set di **dati**seguente.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="a1dc2-117">Per semplicità vengono mostrate solo le proprietà rilevanti.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="a1dc2-118">Nel **set di dati** generato la proprietà **IsPrimaryKey** è impostata su **false** per il vincolo UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="a1dc2-119">La proprietà **Unique** della colonna indica che i valori della colonna **CustomerID** devono essere univoci, ma possono essere un riferimento null, come specificato dalla proprietà **AllowDBNull** della colonna.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="a1dc2-120">Se si modifica lo schema e si imposta il valore dell'attributo **msdata: PrimaryKey** facoltativo su **true**, viene creato il vincolo UNIQUE nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="a1dc2-121">La proprietà della colonna **AllowDBNull** è impostata su **false**e la proprietà **IsPrimaryKey** del vincolo è impostata su **true**, rendendo quindi la colonna **CustomerID** una colonna chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="a1dc2-122">È possibile specificare un vincolo univoco per una combinazione di elementi o attributi nell'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="a1dc2-123">Nell'esempio seguente viene illustrato come specificare che una combinazione di valori **CustomerID** e **CompanyName** deve essere univoca per tutti **i clienti** in qualsiasi istanza, aggiungendo un altro elemento **xs: Field** nello schema.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="a1dc2-124">Si tratta del vincolo creato nel **set di dati**risultante.</span><span class="sxs-lookup"><span data-stu-id="a1dc2-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1dc2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1dc2-125">See also</span></span>

- [<span data-ttu-id="a1dc2-126">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="a1dc2-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="a1dc2-127">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="a1dc2-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="a1dc2-128">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a1dc2-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
