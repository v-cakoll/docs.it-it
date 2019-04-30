---
title: Generazione di relazioni tra dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 29c0e9ee96c376c6da392692febccbbae3c6a33f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034320"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="6c153-102">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="6c153-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="6c153-103">In un tipo <xref:System.Data.DataSet> è possibile stabilire un'associazione tra due o più colonne creando una relazione padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="6c153-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="6c153-104">Esistono tre modi per rappresentare un **set di dati** relazione all'interno di uno schema di XML Schema definition language (XSD):</span><span class="sxs-lookup"><span data-stu-id="6c153-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="6c153-105">Specificare tipi complessi annidati.</span><span class="sxs-lookup"><span data-stu-id="6c153-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="6c153-106">Usare la **msdata: Relationship** annotazione.</span><span class="sxs-lookup"><span data-stu-id="6c153-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="6c153-107">Specificare un **xs: keyref** senza il **msdata: ConstraintOnly** annotazione.</span><span class="sxs-lookup"><span data-stu-id="6c153-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="6c153-108">Tipi complessi annidati</span><span class="sxs-lookup"><span data-stu-id="6c153-108">Nested Complex Types</span></span>  
 <span data-ttu-id="6c153-109">Le definizioni di tipi complessi annidati in uno schema indicano le relazioni padre-figlio degli elementi.</span><span class="sxs-lookup"><span data-stu-id="6c153-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="6c153-110">Il seguente frammento di XML Schema indica che **OrderDetail** è un elemento figlio delle **ordine** elemento.</span><span class="sxs-lookup"><span data-stu-id="6c153-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="6c153-111">Il processo di mapping dello Schema XML crea tabelle i **set di dati** che corrispondono ai tipi complessi annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="6c153-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="6c153-112">Crea anche colonne aggiuntive che vengono usate come elemento padre**-** colonne figlio per le tabelle generate.</span><span class="sxs-lookup"><span data-stu-id="6c153-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="6c153-113">Si noti che questi padre**-** colonne figlio specificare relazioni, che non è la stessa funzione primari/chiave vincoli di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="6c153-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="6c153-114">Annotazione msdata:Relationship</span><span class="sxs-lookup"><span data-stu-id="6c153-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="6c153-115">Il **msdata: Relationship** annotazione consente di specificare esplicitamente relazioni padre-figlio tra gli elementi nello schema che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="6c153-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="6c153-116">L'esempio seguente mostra la struttura del **relazione** elemento.</span><span class="sxs-lookup"><span data-stu-id="6c153-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="6c153-117">Gli attributi del **msdata: Relationship** annotazione identificare gli elementi coinvolti nella relazione padre-figlio, nonché come le **vlastnosti parentkey** e **childkey** gli elementi e attributi coinvolti nella relazione.</span><span class="sxs-lookup"><span data-stu-id="6c153-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="6c153-118">Il processo di mapping utilizza queste informazioni per generare le tabelle di **set di dati** e creare la relazione chiave primaria/esterna chiave tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="6c153-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="6c153-119">Ad esempio, il seguente frammento di schema specifica **ordine** e **OrderDetail** elementi allo stesso livello (non annidati).</span><span class="sxs-lookup"><span data-stu-id="6c153-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="6c153-120">Lo schema specifica un **msdata: Relationship** annotazione, che specifica la relazione padre-figlio tra questi due elementi.</span><span class="sxs-lookup"><span data-stu-id="6c153-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="6c153-121">In questo caso, deve essere specificata una relazione esplicita mediante il **msdata: Relationship** annotazione.</span><span class="sxs-lookup"><span data-stu-id="6c153-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="6c153-122">Il processo di mapping utilizza il **relazione** elemento per creare una relazione padre-figlio tra la **OrderNumber** colonna il **ordine** tabella e il **OrderNo** colonna il **OrderDetail** tabella il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6c153-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="6c153-123">Il processo di mapping consente solo di specificare la relazione. Non specifica automaticamente alcun vincolo sui valori di tali colonne, a differenza di quanto avviene mediante i vincoli di chiave primaria/chiave esterna nei database relazionali.</span><span class="sxs-lookup"><span data-stu-id="6c153-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="6c153-124">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="6c153-124">In This Section</span></span>  
 [<span data-ttu-id="6c153-125">Mapping di relazioni implicite tra elementi di schemi annidati</span><span class="sxs-lookup"><span data-stu-id="6c153-125">Map Implicit Relations Between Nested Schema Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="6c153-126">Descrive i vincoli e relazioni creati implicitamente in un **set di dati** quando sono presenti elementi annidati nello Schema XML.</span><span class="sxs-lookup"><span data-stu-id="6c153-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="6c153-127">Mapping di relazioni specificate per elementi annidati</span><span class="sxs-lookup"><span data-stu-id="6c153-127">Map Relations Specified for Nested Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="6c153-128">Viene descritto come impostare esplicitamente le relazioni un **set di dati** per gli elementi annidati di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="6c153-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="6c153-129">Specifica di relazioni tra elementi senza alcun annidamento</span><span class="sxs-lookup"><span data-stu-id="6c153-129">Specify Relations Between Elements with No Nesting</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="6c153-130">Viene descritto come creare le relazioni in un **set di dati** tra gli elementi di XML Schema che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="6c153-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="6c153-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6c153-131">Related Sections</span></span>  
 [<span data-ttu-id="6c153-132">Derivazione della struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="6c153-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="6c153-133">Viene descritta la struttura relazionale, o schema, di un **set di dati** che viene creato da schema di XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="6c153-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="6c153-134">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="6c153-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="6c153-135">Vengono descritti gli elementi di XML Schema utilizzati per creare i vincoli di chiave univoci ed esterni in una **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6c153-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c153-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c153-136">See also</span></span>

- [<span data-ttu-id="6c153-137">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="6c153-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
