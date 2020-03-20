---
title: Mapping di relazioni implicite tra elementi di schemi annidati
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150963"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="ccef8-102">Mapping di relazioni implicite tra elementi di schemi annidati</span><span class="sxs-lookup"><span data-stu-id="ccef8-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="ccef8-103">È possibile che in uno schema XSD (XML Schema Definition Language) siano presenti tipi complessi annidati uno all'interno dell'altro.</span><span class="sxs-lookup"><span data-stu-id="ccef8-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="ccef8-104">In questo caso, le impostazioni di mapping predefinite vengono applicate dal processo di mapping e nel tipo <xref:System.Data.DataSet> vengono creati i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="ccef8-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="ccef8-105">Una tabella per ogni tipo complesso (padre e figlio).</span><span class="sxs-lookup"><span data-stu-id="ccef8-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="ccef8-106">Se nell'elemento padre non esiste alcun vincolo univoco, una colonna di chiave primaria aggiuntiva per ogni definizione di tabella denominata *NomeTabella*_Id dove *NomeTabella* è il nome della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="ccef8-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="ccef8-107">Un vincolo di chiave primaria nella tabella padre che identifica la colonna aggiuntiva come chiave primaria (impostando la proprietà **IsPrimaryKey** su **True**).</span><span class="sxs-lookup"><span data-stu-id="ccef8-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="ccef8-108">Il vincolo viene denominato Constraint\#, dove \# rappresenta 1, 2, 3 e così via.</span><span class="sxs-lookup"><span data-stu-id="ccef8-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="ccef8-109">Il nome predefinito del primo vincolo, ad esempio, è Constraint1.</span><span class="sxs-lookup"><span data-stu-id="ccef8-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="ccef8-110">Un vincolo di chiave esterna nella tabella figlio che consenta di identificare la colonna aggiuntiva come chiave esterna contenente riferimenti alla chiave primaria della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="ccef8-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="ccef8-111">Il vincolo è denominato *ParentTable_ChildTable* dove *ParentTable* è il nome della tabella padre e *ChildTable* è il nome della tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="ccef8-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="ccef8-112">Una relazione di dati tra le tabelle padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="ccef8-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="ccef8-113">Nell'esempio seguente viene illustrato uno schema in cui **OrderDetail** è un elemento figlio **Order**.</span><span class="sxs-lookup"><span data-stu-id="ccef8-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="ccef8-114">Il processo di mapping dello schema XML crea quanto segue nel **DataSet**:</span><span class="sxs-lookup"><span data-stu-id="ccef8-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="ccef8-115">Una tabella **Order** e **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="ccef8-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="ccef8-116">Un vincolo univoco nella tabella **Order.**</span><span class="sxs-lookup"><span data-stu-id="ccef8-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="ccef8-117">Si noti che la proprietà **IsPrimaryKey** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="ccef8-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="ccef8-118">Un vincolo di chiave esterna nella tabella **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="ccef8-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- <span data-ttu-id="ccef8-119">Relazione tra le tabelle **Order** e **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="ccef8-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="ccef8-120">Il **Nested** proprietà per questa relazione è impostata su **True** perché il **Order** e **OrderDetail** elementi sono annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="ccef8-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ccef8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccef8-121">See also</span></span>

- [<span data-ttu-id="ccef8-122">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="ccef8-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="ccef8-123">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="ccef8-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="ccef8-124">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ccef8-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
