---
title: Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150935"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="49e12-102">Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="49e12-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="49e12-103">In uno schema, è possibile specificare un vincolo di chiave su un elemento o un attributo utilizzando l'elemento **key.**</span><span class="sxs-lookup"><span data-stu-id="49e12-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="49e12-104">È necessario che nell'elemento o nell'attributo per cui viene specificato il vincolo siano presenti valori univoci in qualsiasi istanza dello schema e che non sia presente alcun valore null.</span><span class="sxs-lookup"><span data-stu-id="49e12-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="49e12-105">Il vincolo key è simile al vincolo univoco, ma nella colonna per cui viene specificato un vincolo key non sono consentiti valori null.</span><span class="sxs-lookup"><span data-stu-id="49e12-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="49e12-106">Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **key.**</span><span class="sxs-lookup"><span data-stu-id="49e12-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="49e12-107">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="49e12-107">Attribute name</span></span>|<span data-ttu-id="49e12-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49e12-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="49e12-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="49e12-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="49e12-110">Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="49e12-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="49e12-111">In caso contrario, l'attributo **name** fornisce il valore del nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="49e12-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="49e12-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="49e12-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="49e12-113">Se `PrimaryKey="true"` è presente, la proprietà del vincolo **IsPrimaryKey** è impostata su **true**, rendendola una chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="49e12-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="49e12-114">La proprietà della colonna **AllowDBNull** è impostata su **false**, perché le chiavi primarie non possono avere valori null.</span><span class="sxs-lookup"><span data-stu-id="49e12-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="49e12-115">Nella conversione dello schema in cui viene specificato un vincolo di chiave, il processo di mapping crea un vincolo univoco nella tabella con la proprietà di colonna **AllowDBNull** impostata su **false** per ogni colonna nel vincolo.</span><span class="sxs-lookup"><span data-stu-id="49e12-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="49e12-116">Anche la proprietà **IsPrimaryKey** del vincolo univoco è `msdata:PrimaryKey="true"` impostata su **false,** a meno che non sia stato specificato nell'elemento **chiave.**</span><span class="sxs-lookup"><span data-stu-id="49e12-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="49e12-117">Queste impostazioni sono identiche a quelle di un vincolo univoco nello schema in cui `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="49e12-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="49e12-118">Nell'esempio di schema seguente, l'elemento **key** specifica il vincolo di chiave per il **CustomerID** elemento.</span><span class="sxs-lookup"><span data-stu-id="49e12-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>
```  
  
 <span data-ttu-id="49e12-119">L'elemento **key** specifica che i valori dell'elemento figlio **CustomerID** dell'elemento **Customers** devono avere valori univoci e non possono avere valori null.</span><span class="sxs-lookup"><span data-stu-id="49e12-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="49e12-120">Durante la conversione dello schema XSD (XML Schema Definition Language), la seguente tabella viene creata dal processo di mapping:</span><span class="sxs-lookup"><span data-stu-id="49e12-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="49e12-121">Il mapping dello schema XML crea inoltre un **uniqueConstraint** nella <xref:System.Data.DataSet>colonna **CustomerID,** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="49e12-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="49e12-122">Per semplicità vengono mostrate solo le proprietà rilevanti.</span><span class="sxs-lookup"><span data-stu-id="49e12-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="49e12-123">Nel **DataSet** generato, la proprietà **IsPrimaryKey** di **UniqueConstraint** viene impostata `msdata:PrimaryKey="true"` su **true** perché lo schema specifica nell'elemento **key.**</span><span class="sxs-lookup"><span data-stu-id="49e12-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="49e12-124">Il valore della proprietà **ConstraintName** di **UniqueConstraint** nel **DataSet** è il valore dell'attributo **msdata:ConstraintName** specificato nell'elemento **key** nello schema.</span><span class="sxs-lookup"><span data-stu-id="49e12-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e12-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e12-125">See also</span></span>

- [<span data-ttu-id="49e12-126">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="49e12-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="49e12-127">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="49e12-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="49e12-128">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="49e12-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
