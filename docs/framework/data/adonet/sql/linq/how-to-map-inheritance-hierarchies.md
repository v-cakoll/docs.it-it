---
title: 'Procedura: eseguire il mapping di gerarchie di ereditarietà'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 737cb8743d8fd9c93cd46ebf50fba3fe554a35f2
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634664"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="5669c-102">Procedura: eseguire il mapping di gerarchie di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="5669c-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="5669c-103">Per implementare il mapping di ereditarietà in LINQ, è necessario specificare gli attributi e le proprietà dell'attributo sulla classe radice della gerarchia di ereditarietà, come descritto nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="5669c-103">To implement inheritance mapping in LINQ, you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="5669c-104">Gli sviluppatori che usano Visual Studio possono usare i Object Relational Designer per eseguire il mapping delle gerarchie di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="5669c-104">Developers using Visual Studio can use the Object Relational Designer to map inheritance hierarchies.</span></span> <span data-ttu-id="5669c-105">Vedere [procedura: configurare l'ereditarietà tramite O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="5669c-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5669c-106">Non sono richiesti attributi o proprietà speciali sulle sottoclassi.</span><span class="sxs-lookup"><span data-stu-id="5669c-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="5669c-107">Notare, in particolare, che le sottoclassi non dispongono dell'attributo <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5669c-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="5669c-108">Per eseguire il mapping di una gerarchia di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="5669c-108">To map an inheritance hierarchy</span></span>  
  
1. <span data-ttu-id="5669c-109">Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla classe radice.</span><span class="sxs-lookup"><span data-stu-id="5669c-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2. <span data-ttu-id="5669c-110">Aggiungere inoltre alla classe radice un attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> per ogni classe nella struttura gerarchica.</span><span class="sxs-lookup"><span data-stu-id="5669c-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3. <span data-ttu-id="5669c-111">Per ogni attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> definire una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.</span><span class="sxs-lookup"><span data-stu-id="5669c-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="5669c-112">Questa proprietà contiene un valore che viene visualizzato nella colonna <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> della tabella di database per indicare la classe o sottoclasse a cui appartiene questa riga di dati.</span><span class="sxs-lookup"><span data-stu-id="5669c-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4. <span data-ttu-id="5669c-113">Per ogni attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> aggiungere inoltre una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="5669c-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="5669c-114">Questa proprietà contiene un valore che specifica a quale classe o sottoclasse corrisponde il valore della chiave.</span><span class="sxs-lookup"><span data-stu-id="5669c-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5. <span data-ttu-id="5669c-115">Aggiungere una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> solo a uno degli attributi <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="5669c-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="5669c-116">Questa proprietà serve a designare un mapping di *fallback* quando il valore del discriminatore della tabella di database non corrisponde ad alcun valore <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> nei mapping di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="5669c-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6. <span data-ttu-id="5669c-117">Aggiungere una proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> per un attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5669c-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="5669c-118">Questa proprietà indica che la colonna specificata contiene il valore <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.</span><span class="sxs-lookup"><span data-stu-id="5669c-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5669c-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="5669c-119">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5669c-120">Se si utilizza Visual Studio, è possibile utilizzare il Object Relational Designer per configurare l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="5669c-120">If you are using Visual Studio, you can use the Object Relational Designer to configure inheritance.</span></span> <span data-ttu-id="5669c-121">Vedere [procedura: configurare l'ereditarietà tramite O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="5669c-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="5669c-122">Nell'esempio di codice seguente, `Vehicle` viene definito come classe radice e i passaggi precedenti sono stati implementati per descrivere la gerarchia per LINQ.</span><span class="sxs-lookup"><span data-stu-id="5669c-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for LINQ.</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5669c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5669c-123">See also</span></span>

- [<span data-ttu-id="5669c-124">Supporto dell'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="5669c-124">Inheritance Support</span></span>](inheritance-support.md)
- [<span data-ttu-id="5669c-125">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="5669c-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
