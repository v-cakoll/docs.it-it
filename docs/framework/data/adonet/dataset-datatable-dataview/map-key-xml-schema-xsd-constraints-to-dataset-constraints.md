---
title: Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6b999e6b1d6d73f107b7e1f4cb0d7e14c099a1f6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="ffaa2-102">Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="ffaa2-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="ffaa2-103">In uno schema, è possibile specificare un vincolo di chiave su un elemento o attributo mediante la **chiave** elemento.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="ffaa2-104">È necessario che nell'elemento o nell'attributo per cui viene specificato il vincolo siano presenti valori univoci in qualsiasi istanza dello schema e che non sia presente alcun valore null.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="ffaa2-105">Il vincolo key è simile al vincolo univoco, ma nella colonna per cui viene specificato un vincolo key non sono consentiti valori null.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="ffaa2-106">Nella tabella seguente vengono illustrati il **msdata** gli attributi che è possibile specificare nel **chiave** elemento.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="ffaa2-107">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="ffaa2-107">Attribute name</span></span>|<span data-ttu-id="ffaa2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffaa2-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ffaa2-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="ffaa2-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="ffaa2-110">Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="ffaa2-111">In caso contrario, il **nome** attributo fornisce il valore del nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="ffaa2-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="ffaa2-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="ffaa2-113">Se `PrimaryKey="true"` è presente, il **IsPrimaryKey** vincolo è impostata su **true**, rendendo così una chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="ffaa2-114">Il **AllowDBNull** colonna è impostata su **false**, perché le chiavi primarie non sono consentiti valori null.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="ffaa2-115">Durante la conversione dello schema in cui è stato specificato un vincolo di chiave, il processo di mapping consente di creare un vincolo unique nella tabella con il **AllowDBNull** proprietà column impostata sulla **false** per ogni colonna di vincolo.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="ffaa2-116">Il **IsPrimaryKey** anche proprietà del vincolo unique è impostata su **false** a meno che non è stato specificato `msdata:PrimaryKey="true"` sul **chiave** elemento.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="ffaa2-117">Queste impostazioni sono identiche a quelle di un vincolo univoco nello schema in cui `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="ffaa2-118">Nell'esempio di schema seguente, il **chiave** elemento specifica il vincolo di chiave per la **CustomerID** elemento.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="ffaa2-119">Il **chiave** elemento specifica che i valori del **CustomerID** elemento figlio dell'elemento di **clienti** elemento deve contenere valori univoci e non può contenere valori null.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="ffaa2-120">Durante la conversione dello schema XSD (XML Schema Definition Language), la seguente tabella viene creata dal processo di mapping:</span><span class="sxs-lookup"><span data-stu-id="ffaa2-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="ffaa2-121">Il mapping di XML Schema crea anche un **UniqueConstraint** sul **CustomerID** colonna, come illustrato di seguito <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ffaa2-122">Per semplicità vengono mostrate solo le proprietà rilevanti.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
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
  
 <span data-ttu-id="ffaa2-123">Nel **DataSet** generato, il **IsPrimaryKey** proprietà del **UniqueConstraint** è impostato su **true** perché lo schema specifica `msdata:PrimaryKey="true"` nel **chiave** elemento.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="ffaa2-124">Il valore della **ConstraintName** proprietà del **UniqueConstraint** nel **set di dati** è il valore della **msdata: ConstraintName** attributo specificato nella **chiave** elemento nello schema.</span><span class="sxs-lookup"><span data-stu-id="ffaa2-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffaa2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffaa2-125">See Also</span></span>  
 [<span data-ttu-id="ffaa2-126">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="ffaa2-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="ffaa2-127">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="ffaa2-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="ffaa2-128">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ffaa2-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
