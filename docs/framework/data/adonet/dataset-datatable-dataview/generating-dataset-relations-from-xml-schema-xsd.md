---
title: Generazione di relazioni tra dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151130"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="98418-102">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="98418-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="98418-103">In un tipo <xref:System.Data.DataSet> è possibile stabilire un'associazione tra due o più colonne creando una relazione padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="98418-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="98418-104">Esistono tre modi per rappresentare una relazione **DataSet** all'interno di uno schema XSD (XML Schema Definition Language):</span><span class="sxs-lookup"><span data-stu-id="98418-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="98418-105">Specificare tipi complessi annidati.</span><span class="sxs-lookup"><span data-stu-id="98418-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="98418-106">Utilizzare l'annotazione **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="98418-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="98418-107">Specificare **un xs:keyref** senza l'annotazione **msdata:ConstraintOnly.**</span><span class="sxs-lookup"><span data-stu-id="98418-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="98418-108">Tipi complessi annidati</span><span class="sxs-lookup"><span data-stu-id="98418-108">Nested Complex Types</span></span>  
 <span data-ttu-id="98418-109">Le definizioni di tipi complessi annidati in uno schema indicano le relazioni padre-figlio degli elementi.</span><span class="sxs-lookup"><span data-stu-id="98418-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="98418-110">Il frammento XML Schema seguente mostra che **OrderDetail** è un elemento figlio del **Order** elemento.</span><span class="sxs-lookup"><span data-stu-id="98418-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="98418-111">Il processo di mapping dello schema XML crea tabelle nel **DataSet** che corrispondono ai tipi complessi annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="98418-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="98418-112">Vengono inoltre create colonne aggiuntive**-** utilizzate come colonne figlio padre per le tabelle generate.</span><span class="sxs-lookup"><span data-stu-id="98418-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="98418-113">Si noti**-** che queste colonne figlio padre specificano relazioni, che non corrisponde alla specifica di vincoli di chiave primaria/chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="98418-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="98418-114">Annotazione msdata:Relationship</span><span class="sxs-lookup"><span data-stu-id="98418-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="98418-115">L'annotazione **msdata:Relationship** consente di specificare in modo esplicito le relazioni padre-figlio tra gli elementi dello schema che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="98418-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="98418-116">Nell'esempio seguente viene illustrata la struttura dell'elemento **Relationship.**</span><span class="sxs-lookup"><span data-stu-id="98418-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="98418-117">Gli attributi dell'annotazione **msdata:Relationship identificano** gli elementi coinvolti nella relazione padre-figlio, nonché gli elementi e gli attributi **parentkey** e **childkey** coinvolti nella relazione.</span><span class="sxs-lookup"><span data-stu-id="98418-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="98418-118">Il processo di mapping utilizza queste informazioni per generare tabelle nel **DataSet** e per creare la relazione chiave primaria/chiave esterna tra queste tabelle.</span><span class="sxs-lookup"><span data-stu-id="98418-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="98418-119">Ad esempio, il frammento di schema seguente specifica **Order** e **OrderDetail** elementi allo stesso livello (non annidati).</span><span class="sxs-lookup"><span data-stu-id="98418-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="98418-120">Lo schema specifica **un'annotazione msdata:Relationship,** che specifica la relazione padre-figlio tra questi due elementi.</span><span class="sxs-lookup"><span data-stu-id="98418-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="98418-121">In questo caso, è necessario specificare una relazione esplicita utilizzando l'annotazione **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="98418-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="98418-122">Il processo di mapping utilizza l'elemento **Relationship** per creare una relazione padre-figlio tra la colonna **OrderNumber** della tabella **Order** e la colonna **OrderNo** della tabella **OrderDetail** del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="98418-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="98418-123">Il processo di mapping consente solo di specificare la relazione. Non specifica automaticamente alcun vincolo sui valori di tali colonne, a differenza di quanto avviene mediante i vincoli di chiave primaria/chiave esterna nei database relazionali.</span><span class="sxs-lookup"><span data-stu-id="98418-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="98418-124">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="98418-124">In This Section</span></span>  
 [<span data-ttu-id="98418-125">Mapping di relazioni implicite tra elementi di schemi annidati</span><span class="sxs-lookup"><span data-stu-id="98418-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="98418-126">Vengono descritti i vincoli e le relazioni creati in modo implicito in un **DataSet** quando gli elementi annidati vengono rilevati nello schema XML.</span><span class="sxs-lookup"><span data-stu-id="98418-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="98418-127">Mapping di relazioni specificate per elementi annidati</span><span class="sxs-lookup"><span data-stu-id="98418-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="98418-128">Viene descritto come impostare in modo esplicito le relazioni in un **DataSet** per gli elementi annidati nello schema XML.</span><span class="sxs-lookup"><span data-stu-id="98418-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="98418-129">Specifica di relazioni tra elementi senza alcun annidamento</span><span class="sxs-lookup"><span data-stu-id="98418-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="98418-130">Viene descritto come creare relazioni in un **DataSet** tra elementi XML Schema non annidati.</span><span class="sxs-lookup"><span data-stu-id="98418-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="98418-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="98418-131">Related Sections</span></span>  
 [<span data-ttu-id="98418-132">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="98418-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="98418-133">Viene descritta la struttura relazionale, o schema, di un **DataSet** creato dallo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="98418-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="98418-134">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="98418-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="98418-135">Vengono descritti gli elementi dello schema XML utilizzati per creare vincoli di chiave univoca ed esterna in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="98418-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98418-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98418-136">See also</span></span>

- [<span data-ttu-id="98418-137">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98418-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
