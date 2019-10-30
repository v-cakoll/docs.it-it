---
title: Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 93f766003326fd41357581196015fd58c71d7508
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040379"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="cc244-102">Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="cc244-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="cc244-103">L'elemento **keyref** consente di stabilire collegamenti tra gli elementi all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="cc244-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="cc244-104">Questo elemento ha quindi una funzione simile a quella della relazione di chiave esterna in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="cc244-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="cc244-105">Se uno schema specifica l'elemento **keyref** , l'elemento viene convertito durante il processo di mapping dello schema a un vincolo di chiave esterna corrispondente sulle colonne delle tabelle del <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="cc244-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="cc244-106">Per impostazione predefinita, l'elemento **keyref** genera anche una relazione, con le proprietà **ParentTable**, **ChildTable**, **parentColumn**e **ChildColumn vengono specificate** specificate nella relazione.</span><span class="sxs-lookup"><span data-stu-id="cc244-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="cc244-107">Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **keyref** .</span><span class="sxs-lookup"><span data-stu-id="cc244-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="cc244-108">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="cc244-108">Attribute name</span></span>|<span data-ttu-id="cc244-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc244-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="cc244-110">**msdata: ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="cc244-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="cc244-111">Se **ConstraintOnly = "true"** viene specificato nell'elemento **keyref** dello schema, viene creato un vincolo, ma non viene creata alcuna relazione.</span><span class="sxs-lookup"><span data-stu-id="cc244-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="cc244-112">Se questo attributo non viene specificato (o è impostato su **false**), nel **set di dati**vengono creati sia il vincolo che la relazione.</span><span class="sxs-lookup"><span data-stu-id="cc244-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="cc244-113">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="cc244-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="cc244-114">Se viene specificato l'attributo **ConstraintName** , il relativo valore viene usato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="cc244-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="cc244-115">In caso contrario, l'attributo **Name** dell'elemento **keyref** nello schema fornisce il nome del vincolo nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="cc244-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="cc244-116">**msdata: UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="cc244-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="cc244-117">Se l'attributo **UpdateRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà Constraint **UpdateRule** nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="cc244-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="cc244-118">In caso contrario, la proprietà **UpdateRule** viene impostata su **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="cc244-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="cc244-119">**msdata: DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="cc244-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="cc244-120">Se l'attributo **DeleteRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà Constraint **DeleteRule** nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="cc244-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="cc244-121">In caso contrario, la proprietà **DeleteRule** viene impostata su **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="cc244-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="cc244-122">**msdata: AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="cc244-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="cc244-123">Se l'attributo **AcceptRejectRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà Constraint **AcceptRejectRule** nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="cc244-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="cc244-124">In caso contrario, la proprietà **AcceptRejectRule** è impostata su **None**.</span><span class="sxs-lookup"><span data-stu-id="cc244-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="cc244-125">Nell'esempio seguente è contenuto uno schema che specifica le relazioni **Key** e **keyref** tra l'elemento figlio **OrderNumber** dell'elemento **Order** e l'elemento figlio **OrderNo** di **OrderDetail** elemento.</span><span class="sxs-lookup"><span data-stu-id="cc244-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="cc244-126">Nell'esempio, l'elemento figlio **OrderNumber** dell'elemento **OrderDetail** si riferisce all'elemento figlio Key **OrderNo** dell'elemento **Order** .</span><span class="sxs-lookup"><span data-stu-id="cc244-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="cc244-127">Il processo di mapping dello schema XSD (XML Schema Definition Language) produce il **set di dati** seguente con due tabelle:</span><span class="sxs-lookup"><span data-stu-id="cc244-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="cc244-128">Inoltre, il **set di dati** definisce i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc244-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="cc244-129">Vincolo UNIQUE nella tabella **Order** .</span><span class="sxs-lookup"><span data-stu-id="cc244-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="cc244-130">Relazione tra le tabelle **Order** e **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="cc244-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="cc244-131">La proprietà **nidificata** è impostata su **false** perché i due elementi non sono annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="cc244-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="cc244-132">Vincolo FOREIGN KEY nella tabella **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="cc244-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cc244-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc244-133">See also</span></span>

- [<span data-ttu-id="cc244-134">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="cc244-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="cc244-135">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="cc244-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="cc244-136">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cc244-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
