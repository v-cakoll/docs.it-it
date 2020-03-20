---
title: Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150883"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="0db82-102">Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="0db82-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="0db82-103">L'elemento **keyref** consente di stabilire collegamenti tra gli elementi all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="0db82-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="0db82-104">Questo elemento ha quindi una funzione simile a quella della relazione di chiave esterna in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="0db82-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="0db82-105">Se uno schema specifica l'elemento **keyref,** l'elemento viene convertito durante il processo di mapping <xref:System.Data.DataSet>dello schema in un vincolo di chiave esterna corrispondente nelle colonne delle tabelle dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="0db82-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0db82-106">Per impostazione predefinita, l'elemento **keyref** genera anche una relazione con le proprietà **ParentTable**, **ChildTable**, **ParentColumn**e **ChildColumn** specificate nella relazione.</span><span class="sxs-lookup"><span data-stu-id="0db82-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="0db82-107">Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **keyref.**</span><span class="sxs-lookup"><span data-stu-id="0db82-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="0db82-108">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="0db82-108">Attribute name</span></span>|<span data-ttu-id="0db82-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0db82-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0db82-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="0db82-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="0db82-111">Se nell'elemento **keyref** dello schema viene specificato **"true",** viene creato un vincolo, ma non viene creata alcuna relazione.</span><span class="sxs-lookup"><span data-stu-id="0db82-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="0db82-112">Se questo attributo non è specificato (o è impostato su **False**), sia il vincolo che la relazione vengono creati nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0db82-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="0db82-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="0db82-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="0db82-114">Se viene specificato l'attributo **ConstraintName,** il relativo valore viene utilizzato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="0db82-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="0db82-115">In caso contrario, l'attributo **name** dell'elemento **keyref** nello schema fornisce il nome del vincolo nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0db82-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="0db82-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="0db82-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="0db82-117">Se l'attributo **UpdateRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà del vincolo **UpdateRule** nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0db82-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="0db82-118">In caso contrario, la proprietà **UpdateRule** viene impostata su **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="0db82-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="0db82-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="0db82-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="0db82-120">Se l'attributo **DeleteRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà del vincolo **DeleteRule** nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0db82-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="0db82-121">In caso contrario, la proprietà **DeleteRule** viene impostata su **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="0db82-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="0db82-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="0db82-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="0db82-123">Se l'attributo **AcceptRejectRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà del vincolo **AcceptRejectRule** nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0db82-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="0db82-124">In caso contrario, la proprietà **AcceptRejectRule** viene impostata su **None**.</span><span class="sxs-lookup"><span data-stu-id="0db82-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="0db82-125">L'esempio seguente contiene uno schema che specifica le relazioni **key** e **keyref** tra l'elemento figlio **OrderNumber** dell'elemento **Order** e l'elemento figlio **OrderNo** dell'elemento **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="0db82-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="0db82-126">Nell'esempio, l'elemento figlio **OrderNumber** dell'elemento **OrderDetail** fa riferimento all'elemento figlio **chiave OrderNo** dell'elemento **Order.**</span><span class="sxs-lookup"><span data-stu-id="0db82-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="0db82-127">Il processo di mapping dello schema XSD (XML Schema Definition Language) produce il DataSet seguente con due tabelle:The XML Schema Definition Language (XSD) schema mapping process produces the following **DataSet** with two tables:</span><span class="sxs-lookup"><span data-stu-id="0db82-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="0db82-128">Inoltre, il DataSet definisce i vincoli seguenti:In addition, the **DataSet** defines the following constraints:</span><span class="sxs-lookup"><span data-stu-id="0db82-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="0db82-129">Un vincolo univoco nella tabella **Order.**</span><span class="sxs-lookup"><span data-stu-id="0db82-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="0db82-130">Relazione tra le tabelle **Order** e **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="0db82-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="0db82-131">Il **Nested** proprietà è impostata su **False** perché i due elementi non sono annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="0db82-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="0db82-132">Un vincolo di chiave esterna nella tabella **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="0db82-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0db82-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0db82-133">See also</span></span>

- [<span data-ttu-id="0db82-134">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="0db82-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="0db82-135">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="0db82-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="0db82-136">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0db82-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
