---
title: Post-Schema Compilation Infoset (PSCI, infoset sulla compilazione post-schema)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 7f1bc7f4-401b-459f-9078-f099cc711fde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 77fe1790a4ff2f910a740e969e458549f1fd9642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="post-schema-compilation-infoset"></a><span data-ttu-id="d0f62-102">Post-Schema Compilation Infoset (PSCI, infoset sulla compilazione post-schema)</span><span class="sxs-lookup"><span data-stu-id="d0f62-102">Post-Schema Compilation Infoset</span></span>
<span data-ttu-id="d0f62-103">Il [World Wide Web Consortium (W3C) XML Schema Recommendation](http://go.microsoft.com/fwlink/?linkid=45242) viene illustrato il set di informazioni (infoset) che deve essere esposto per la convalida di pre-schema e di compilazione post-schema.</span><span class="sxs-lookup"><span data-stu-id="d0f62-103">The [World Wide Web Consortium (W3C) XML Schema Recommendation](http://go.microsoft.com/fwlink/?linkid=45242) discusses the information set (infoset) that must be exposed for pre-schema validation and post-schema compilation.</span></span> <span data-ttu-id="d0f62-104">Il modello SOM (Schema Object Model) XML visualizza questa esposizione prima e dopo che venga chiamato il metodo <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> del tipo <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="d0f62-104">The XML Schema Object Model (SOM) views this exposure before and after the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called.</span></span>  
  
 <span data-ttu-id="d0f62-105">L'infoset sulla convalida pre-schema viene compilato durante la modifica dello schema.</span><span class="sxs-lookup"><span data-stu-id="d0f62-105">The pre-schema validation infoset is built during the editing of the schema.</span></span> <span data-ttu-id="d0f62-106">L'infoset sulla compilazione post-schema viene generato dopo la chiamata al metodo <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> del tipo <xref:System.Xml.Schema.XmlSchemaSet>, durante la compilazione dello schema, e viene esposto come proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0f62-106">The post-schema compilation infoset is generated after the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called, during compilation of the schema, and is exposed as properties.</span></span>  
  
 <span data-ttu-id="d0f62-107">Il modello SOM è il modello a oggetti che rappresenta gli infoset di convalida pre-schema e di compilazione post-schema. Include le classi nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0f62-107">The SOM is the object model that represents the pre-schema validation and post-schema compilation infosets; it consists of the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d0f62-108">Tutte le proprietà di lettura e scrittura delle classi nello spazio dei nomi <xref:System.Xml.Schema> appartengono all'infoset sulla convalida pre-schema, mentre tutte le proprietà delle classi nello spazio dei nomi <xref:System.Xml.Schema> appartengono all'infoset sulla compilazione post-schema.</span><span class="sxs-lookup"><span data-stu-id="d0f62-108">All read and write properties of classes in the <xref:System.Xml.Schema> namespace belong to the pre-schema validation infoset, while all read-only properties of classes in the <xref:System.Xml.Schema> namespace belong to the post-schema compilation infoset.</span></span> <span data-ttu-id="d0f62-109">L'eccezione a questa regola è rappresentata dalle seguenti proprietà, che sono proprietà sia di infoset di convalida pre-schema sia di infoset di compilazione post-schema.</span><span class="sxs-lookup"><span data-stu-id="d0f62-109">The exception to this rule are the following properties, which are both pre-schema validation infoset and post-schema compilation infoset properties.</span></span>  
  
|<span data-ttu-id="d0f62-110">Classe</span><span class="sxs-lookup"><span data-stu-id="d0f62-110">Class</span></span>|<span data-ttu-id="d0f62-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d0f62-111">Property</span></span>|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<span data-ttu-id="d0f62-112"><xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="d0f62-112"><xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A></span></span>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<span data-ttu-id="d0f62-113"><xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A></span><span class="sxs-lookup"><span data-stu-id="d0f62-113"><xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A></span></span>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 <span data-ttu-id="d0f62-114">Ad esempio, sia la classe <xref:System.Xml.Schema.XmlSchemaElement> che la classe <xref:System.Xml.Schema.XmlSchemaComplexType> dispongono delle proprietà `BlockResolved` e `FinalResolved`.</span><span class="sxs-lookup"><span data-stu-id="d0f62-114">For example, the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaComplexType> classes both have `BlockResolved` and `FinalResolved` properties.</span></span> <span data-ttu-id="d0f62-115">Tali proprietà vengono usate per conservare i valori delle proprietà `Block` e `Final` dopo che lo schema è stato compilato e convalidato.</span><span class="sxs-lookup"><span data-stu-id="d0f62-115">These properties are used to hold the values for the `Block` and `Final` properties after the schema has been compiled and validated.</span></span> <span data-ttu-id="d0f62-116">Le proprietà `BlockResolved` e `FinalResolved` sono di sola lettura e fanno parte dell'infoset di compilazione post-schema.</span><span class="sxs-lookup"><span data-stu-id="d0f62-116">`BlockResolved` and `FinalResolved` are read-only properties that are part of the post-schema compilation infoset.</span></span>  
  
 <span data-ttu-id="d0f62-117">Nell'esempio seguente viene illustrata la proprietà <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> della classe <xref:System.Xml.Schema.XmlSchemaElement> impostata dopo la convalida dello schema.</span><span class="sxs-lookup"><span data-stu-id="d0f62-117">The following example shows the <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> class set after validating the schema.</span></span> <span data-ttu-id="d0f62-118">Prima della convalida la proprietà contiene un riferimento `null` e la proprietà <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> è impostata sul nome del tipo in questione.</span><span class="sxs-lookup"><span data-stu-id="d0f62-118">Before validation, the property contains a `null` reference, and the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> is set to the name of the type in question.</span></span> <span data-ttu-id="d0f62-119">Dopo la convalida la proprietà <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> viene risolta in un tipo valido e l'oggetto del tipo è disponibile attraverso la proprietà <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0f62-119">After validation, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> is resolved to a valid type, and the type object is available through the <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> property.</span></span>  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d0f62-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0f62-120">See Also</span></span>  
 [<span data-ttu-id="d0f62-121">SOM (Schema Object Model) XML</span><span class="sxs-lookup"><span data-stu-id="d0f62-121">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
