---
title: Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: dcb295aef6d93222e682ef7f720c83963036e795
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229745"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="aa590-102">Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="aa590-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="aa590-103">Il **keyref** elemento consente di stabilire collegamenti tra gli elementi all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="aa590-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="aa590-104">Questo elemento ha quindi una funzione simile a quella della relazione di chiave esterna in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="aa590-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="aa590-105">Se uno schema viene specificato il **keyref** elemento, l'elemento viene convertito durante il processo di mapping dello schema per un vincolo di chiave esterna corrispondente nelle colonne delle tabelle del <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="aa590-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="aa590-106">Per impostazione predefinita, il **keyref** elemento genera anche una relazione, con la **ParentTable**, **ChildTable**, **ParentColumn**e  **ChildColumn** proprietà specificate per la relazione.</span><span class="sxs-lookup"><span data-stu-id="aa590-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="aa590-107">La tabella seguente descrive la **msdata** attributi che è possibile specificare nel **keyref** elemento.</span><span class="sxs-lookup"><span data-stu-id="aa590-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="aa590-108">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="aa590-108">Attribute name</span></span>|<span data-ttu-id="aa590-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa590-109">Description</span></span>|  
|--------------------|-----------------|  
|**<span data-ttu-id="aa590-110">msdata:ConstraintOnly</span><span class="sxs-lookup"><span data-stu-id="aa590-110">msdata:ConstraintOnly</span></span>**|<span data-ttu-id="aa590-111">Se **ConstraintOnly = "true"** viene specificata per il **keyref** elemento nello schema, viene creato un vincolo, ma viene creata alcuna relazione.</span><span class="sxs-lookup"><span data-stu-id="aa590-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="aa590-112">Se questo attributo non è specificato (o è impostata su **False**) sia il vincolo della relazione vengono creati nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="aa590-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|**<span data-ttu-id="aa590-113">msdata:ConstraintName</span><span class="sxs-lookup"><span data-stu-id="aa590-113">msdata:ConstraintName</span></span>**|<span data-ttu-id="aa590-114">Se il **ConstraintName** attributo è specificato, il relativo valore viene utilizzato come nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="aa590-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="aa590-115">In caso contrario, il **name** attributo del **keyref** elemento nello schema fornisce il nome del vincolo nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="aa590-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|**<span data-ttu-id="aa590-116">msdata:UpdateRule</span><span class="sxs-lookup"><span data-stu-id="aa590-116">msdata:UpdateRule</span></span>**|<span data-ttu-id="aa590-117">Se il **UpdateRule** attributo è specificato nella **keyref** elemento nello schema, il relativo valore viene assegnato al **UpdateRule** proprietà vincolo nel  **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="aa590-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="aa590-118">In caso contrario, il **UpdateRule** è impostata su **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="aa590-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|**<span data-ttu-id="aa590-119">msdata:DeleteRule</span><span class="sxs-lookup"><span data-stu-id="aa590-119">msdata:DeleteRule</span></span>**|<span data-ttu-id="aa590-120">Se il **DeleteRule** attributo è specificato nella **keyref** elemento nello schema, il relativo valore viene assegnato al **DeleteRule** proprietà vincolo nel  **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="aa590-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="aa590-121">In caso contrario, il **DeleteRule** è impostata su **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="aa590-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|**<span data-ttu-id="aa590-122">msdata:AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="aa590-122">msdata:AcceptRejectRule</span></span>**|<span data-ttu-id="aa590-123">Se il **AcceptRejectRule** attributo è specificato nella **keyref** elemento nello schema, il relativo valore viene assegnato al **AcceptRejectRule** proprietà vincolo nel  **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="aa590-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="aa590-124">In caso contrario, il **AcceptRejectRule** è impostata su **None**.</span><span class="sxs-lookup"><span data-stu-id="aa590-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="aa590-125">Nell'esempio seguente contiene uno schema che specifica il **chiave** e **keyref** le relazioni tra il **OrderNumber** elemento figlio dell'elemento di **ordine**  elemento e il **OrderNo** elemento figlio dell'elemento il **OrderDetail** elemento.</span><span class="sxs-lookup"><span data-stu-id="aa590-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="aa590-126">Nell'esempio, il **OrderNumber** elemento figlio dell'elemento il **OrderDetail** elemento fa riferimento al **OrderNo** elemento chiave figlio dell'elemento il **ordine**elemento.</span><span class="sxs-lookup"><span data-stu-id="aa590-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="aa590-127">Il processo di mapping dello schema di XML Schema definition language (XSD) produce il seguente **set di dati** con due tabelle:</span><span class="sxs-lookup"><span data-stu-id="aa590-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="aa590-128">Inoltre, il **set di dati** definisce i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa590-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
-   <span data-ttu-id="aa590-129">Un vincolo unique per la **ordine** tabella.</span><span class="sxs-lookup"><span data-stu-id="aa590-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   <span data-ttu-id="aa590-130">Una relazione tra il **ordine** e **OrderDetail** tabelle.</span><span class="sxs-lookup"><span data-stu-id="aa590-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="aa590-131">Il **Nested** è impostata su **False** perché i due elementi non annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="aa590-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   <span data-ttu-id="aa590-132">Un vincolo di chiave esterna nella **OrderDetail** tabella.</span><span class="sxs-lookup"><span data-stu-id="aa590-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aa590-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa590-133">See also</span></span>

- [<span data-ttu-id="aa590-134">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="aa590-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="aa590-135">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="aa590-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="aa590-136">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="aa590-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
