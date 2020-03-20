---
title: Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150844"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="8330d-102">Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="8330d-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="8330d-103">In uno schema XSD (XML Schema Definition Language), l'elemento **unique** specifica il vincolo di unicità su un elemento o un attributo.</span><span class="sxs-lookup"><span data-stu-id="8330d-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="8330d-104">Durante il processo di conversione di un XML Schema in uno schema relazionale, viene eseguito il mapping del vincolo univoco specificato su un elemento o un attributo dell'XML Schema a un vincolo univoco del tipo <xref:System.Data.DataTable> nel tipo <xref:System.Data.DataSet> corrispondente generato.</span><span class="sxs-lookup"><span data-stu-id="8330d-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="8330d-105">Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **univoco.**</span><span class="sxs-lookup"><span data-stu-id="8330d-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="8330d-106">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="8330d-106">Attribute name</span></span>|<span data-ttu-id="8330d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8330d-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8330d-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="8330d-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="8330d-109">Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="8330d-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="8330d-110">In caso contrario, l'attributo **name** fornisce il valore del nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="8330d-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="8330d-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="8330d-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="8330d-112">Se `PrimaryKey="true"` è presente nell'elemento **unique,** viene creato un vincolo univoco con la proprietà **IsPrimaryKey** impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="8330d-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="8330d-113">Nell'esempio seguente viene illustrato uno schema XML che utilizza l'elemento **unique** per specificare un vincolo di unicità.</span><span class="sxs-lookup"><span data-stu-id="8330d-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="8330d-114">L'elemento **unique** nello schema specifica che per tutti gli elementi **Customers** in un'istanza del documento, il valore dell'elemento figlio **CustomerID** deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="8330d-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="8330d-115">Nella compilazione del **DataSet**, il processo di mapping legge questo schema e genera la tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8330d-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="8330d-116">Il processo di mapping crea inoltre un vincolo univoco nella colonna **CustomerID,** come illustrato nel **DataSet**seguente.</span><span class="sxs-lookup"><span data-stu-id="8330d-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="8330d-117">Per semplicità vengono mostrate solo le proprietà rilevanti.</span><span class="sxs-lookup"><span data-stu-id="8330d-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
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
  
 <span data-ttu-id="8330d-118">Nel **DataSet** generato, la proprietà **IsPrimaryKey** è impostata su **False** per il vincolo univoco.</span><span class="sxs-lookup"><span data-stu-id="8330d-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="8330d-119">La proprietà **unique** nella colonna indica che i valori della colonna **CustomerID** devono essere univoci (ma possono essere un riferimento null, come specificato dalla proprietà **AllowDBNull** della colonna).</span><span class="sxs-lookup"><span data-stu-id="8330d-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="8330d-120">Se si modifica lo schema e si imposta il valore facoltativo dell'attributo **msdata:PrimaryKey** su **True**, il vincolo univoco viene creato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="8330d-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="8330d-121">La proprietà della colonna **AllowDBNull** è impostata su **False**e la proprietà **IsPrimaryKey** del vincolo è impostata su **True**, rendendo così la colonna **CustomerID** una colonna di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8330d-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="8330d-122">È possibile specificare un vincolo univoco per una combinazione di elementi o attributi nell'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="8330d-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="8330d-123">Nell'esempio seguente viene illustrato come specificare che una combinazione di **CustomerID** e **CompanyName** valori devono essere univoci per tutti i **clienti** in qualsiasi istanza, aggiungendo un altro **xs:field** elemento nello schema.</span><span class="sxs-lookup"><span data-stu-id="8330d-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="8330d-124">Si tratta del vincolo creato nel **DataSet**risultante.</span><span class="sxs-lookup"><span data-stu-id="8330d-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="8330d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8330d-125">See also</span></span>

- [<span data-ttu-id="8330d-126">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="8330d-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="8330d-127">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="8330d-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="8330d-128">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8330d-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
