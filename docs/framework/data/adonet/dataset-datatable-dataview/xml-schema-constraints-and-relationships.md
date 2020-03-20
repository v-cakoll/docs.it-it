---
title: Vincoli e relazioni di XML Schema
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150714"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="6e4d7-102">Vincoli e relazioni di XML Schema</span><span class="sxs-lookup"><span data-stu-id="6e4d7-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="6e4d7-103">In uno schema XSD (XML Schema Definition Language) è possibile specificare vincoli (vincoli univoci, chiave e keyref) e relazioni (utilizzando l'annotazione **msdata:Relationship).**</span><span class="sxs-lookup"><span data-stu-id="6e4d7-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="6e4d7-104">In questo argomento viene spiegato come vengono interpretati i vincoli e le relazioni specificati in XML Schema per generare il tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="6e4d7-105">In generale, in uno schema XML si specifica l'annotazione **msdata:Relationship** se si desidera generare solo relazioni nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="6e4d7-106">Per ulteriori informazioni, vedere [Generazione di relazioni con DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="6e4d7-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="6e4d7-107">Specificare i vincoli (univoco, key e keyref) se si desidera generare vincoli nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="6e4d7-108">Notare che i vincoli key e keyref vengono usati anche per generare relazioni, come spiegato successivamente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="6e4d7-109">Generazione di una relazione dai vincoli key e keyref</span><span class="sxs-lookup"><span data-stu-id="6e4d7-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="6e4d7-110">Anziché specificare l'annotazione **msdata:Relationship,** è possibile specificare i vincoli key e keyref, utilizzati durante il processo di mapping dello schema XML per generare non solo i vincoli, ma anche la relazione nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="6e4d7-111">Tuttavia, se `msdata:ConstraintOnly="true"` si specifica nell'elemento **keyref,** il **DataSet** includerà solo i vincoli e non includerà la relazione.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="6e4d7-112">Nell'esempio seguente viene illustrato uno schema XML che include gli elementi **Order** e **OrderDetail,** che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="6e4d7-113">Nello schema vengono specificati anche i vincoli key e keyref.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="6e4d7-114">Il **DataSet** generato durante il processo di mapping dello schema XML include le tabelle **Order** e **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="6e4d7-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="6e4d7-115">Inoltre, il **DataSet** include relazioni e vincoli.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="6e4d7-116">Nell'esempio seguente vengono illustrati tali vincoli e relazioni.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="6e4d7-117">Si noti che lo schema non specifica l'annotazione **msdata:Relationship;** i vincoli key e keyref vengono invece utilizzati per generare la relazione.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="6e4d7-118">Nell'esempio di schema precedente, gli elementi **Order** e **OrderDetail** non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="6e4d7-119">Nell'esempio di schema seguente tali elementi sono annidati.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="6e4d7-120">Tuttavia, non viene specificata alcuna annotazione **msdata:Relationship;** pertanto, viene considerata una relazione implicita.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="6e4d7-121">Per ulteriori informazioni, vedere [Eseguire il mapping di relazioni implicite tra elementi dello schema annidati](map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="6e4d7-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="6e4d7-122">Nello schema vengono specificati anche i vincoli key e keyref.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="6e4d7-123">Il DataSet risultante dal processo di mapping dello schema XML include due tabelle:The **DataSet** resulting from the XML Schema mapping process includes two tables:</span><span class="sxs-lookup"><span data-stu-id="6e4d7-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="6e4d7-124">Il **DataSet** include anche le due relazioni (una basata sull'annotazione **msdata:relationship** e l'altra in base ai vincoli key e keyref) e varie vincoli.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="6e4d7-125">Nell'esempio seguente vengono illustrati i vincoli e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-125">The following example shows the relations and constraints.</span></span>  
  
```text
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="6e4d7-126">Se un vincolo keyref che fa riferimento a una tabella nidificata contiene l'annotazione **msdata:IsNested "true",** il **DataSet** creerà una singola relazione nidificata basata sul vincolo keyref e sul vincolo univoco/chiave correlato.</span><span class="sxs-lookup"><span data-stu-id="6e4d7-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4d7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e4d7-127">See also</span></span>

- [<span data-ttu-id="6e4d7-128">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="6e4d7-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="6e4d7-129">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6e4d7-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
