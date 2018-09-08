---
title: Vincoli e relazioni di XML Schema
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: bcb6e257a40040701612b73768a98e056bccd6c5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086998"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="d34e8-102">Vincoli e relazioni di XML Schema</span><span class="sxs-lookup"><span data-stu-id="d34e8-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="d34e8-103">In uno schema di XML Schema definition language (XSD), è possibile specificare vincoli (univoci, vincoli key e keyref) e le relazioni (mediante la **msdata: Relationship** annotazione).</span><span class="sxs-lookup"><span data-stu-id="d34e8-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="d34e8-104">In questo argomento viene spiegato come vengono interpretati i vincoli e le relazioni specificati in XML Schema per generare il tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d34e8-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="d34e8-105">In generale, in uno Schema XML, specificare il **msdata: Relationship** annotazione, se si desidera generare solo le relazioni nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d34e8-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="d34e8-106">Per altre informazioni, vedere [generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="d34e8-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="d34e8-107">Specifica dei vincoli (univoci, key e keyref) se si desidera generare vincoli nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="d34e8-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="d34e8-108">Notare che i vincoli key e keyref vengono usati anche per generare relazioni, come spiegato successivamente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d34e8-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="d34e8-109">Generazione di una relazione dai vincoli key e keyref</span><span class="sxs-lookup"><span data-stu-id="d34e8-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="d34e8-110">Anziché specificare il **msdata: Relationship** annotazione, è possibile specificare i vincoli key e keyref, usati durante il processo di mapping di XML Schema per generare non solo i vincoli, ma anche la relazione nel  **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="d34e8-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="d34e8-111">Tuttavia, se si specifica `msdata:ConstraintOnly="true"` nella **keyref** elemento, il **set di dati** includerà solo i vincoli e non includerà la relazione.</span><span class="sxs-lookup"><span data-stu-id="d34e8-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="d34e8-112">Nell'esempio seguente viene illustrato un XML Schema che include **ordine** e **OrderDetail** elementi, che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="d34e8-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="d34e8-113">Nello schema vengono specificati anche i vincoli key e keyref.</span><span class="sxs-lookup"><span data-stu-id="d34e8-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="d34e8-114">Il **set di dati** che viene generato durante il processo di mapping include di XML Schema il **ordine** e **OrderDetail** tabelle.</span><span class="sxs-lookup"><span data-stu-id="d34e8-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="d34e8-115">Inoltre, il **set di dati** include vincoli e relazioni.</span><span class="sxs-lookup"><span data-stu-id="d34e8-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="d34e8-116">Nell'esempio seguente vengono illustrati tali vincoli e relazioni.</span><span class="sxs-lookup"><span data-stu-id="d34e8-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="d34e8-117">Si noti che lo schema non specifica la **msdata: Relationship** annotazione; al contrario, i vincoli key e keyref vengono usati per generare la relazione.</span><span class="sxs-lookup"><span data-stu-id="d34e8-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
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
  
 <span data-ttu-id="d34e8-118">Nell'esempio di schema precedente, il **ordine** e **OrderDetail** elementi non annidati.</span><span class="sxs-lookup"><span data-stu-id="d34e8-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="d34e8-119">Nell'esempio di schema seguente tali elementi sono annidati.</span><span class="sxs-lookup"><span data-stu-id="d34e8-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="d34e8-120">Tuttavia, nessun **msdata: Relationship** annotazione viene specificata, di conseguenza, si presuppone una relazione implicita.</span><span class="sxs-lookup"><span data-stu-id="d34e8-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="d34e8-121">Per altre informazioni, vedere [implicita delle relazioni tra annidati dello Schema gli elementi della mappa](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d34e8-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="d34e8-122">Nello schema vengono specificati anche i vincoli key e keyref.</span><span class="sxs-lookup"><span data-stu-id="d34e8-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="d34e8-123">Il **set di dati** risultante dal processo di mapping di XML Schema include due tabelle:</span><span class="sxs-lookup"><span data-stu-id="d34e8-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="d34e8-124">Il **set di dati** include anche le due relazioni (uno basato sulle **msdata: Relationship** annotazione e l'altro in base ai vincoli key e keyref) e diversi vincoli.</span><span class="sxs-lookup"><span data-stu-id="d34e8-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="d34e8-125">Nell'esempio seguente vengono illustrati i vincoli e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="d34e8-125">The following example shows the relations and constraints.</span></span>  
  
```  
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
  
 <span data-ttu-id="d34e8-126">Se un vincolo keyref che fa riferimento a una tabella nidificata contiene il **msdata: IsNested = "true"** annotazione, il **set di dati** creerà un'unica relazione annidata basata sul vincolo keyref e vincolo univoco/key correlato.</span><span class="sxs-lookup"><span data-stu-id="d34e8-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34e8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d34e8-127">See Also</span></span>  
 [<span data-ttu-id="d34e8-128">Derivazione della struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="d34e8-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="d34e8-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="d34e8-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
