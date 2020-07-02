---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614971"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="47ed5-101">WPF modifica una chiave primaria quando si visualizzano dati ADO in uno scenario master/dettagli</span><span class="sxs-lookup"><span data-stu-id="47ed5-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

#### <a name="details"></a><span data-ttu-id="47ed5-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="47ed5-102">Details</span></span>

<span data-ttu-id="47ed5-103">Si supponga di avere una raccolta ADO di elementi di tipo `Order`, con una relazione denominata &quot;OrderDetails&quot; che la mette in relazione con una raccolta di elementi di tipo `Detail` tramite la chiave primaria &quot;OrderID&quot;.</span><span class="sxs-lookup"><span data-stu-id="47ed5-103">Suppose you have an ADO collection of items of type `Order`, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type `Detail` via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="47ed5-104">Nell'app WPF, è possibile associare un elenco ai dettagli per un ordine specifico:</span><span class="sxs-lookup"><span data-stu-id="47ed5-104">In your WPF app, you can bind a list control to the details for a given order:</span></span>

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

<span data-ttu-id="47ed5-105">dove DataContext è un `Order`.</span><span class="sxs-lookup"><span data-stu-id="47ed5-105">where the DataContext is an `Order`.</span></span> <span data-ttu-id="47ed5-106">WPF ottiene il valore della `OrderDetails` proprietà, una raccolta D di tutti gli `Detail` elementi la cui `OrderID` corrispondenza corrisponde a dell' `OrderID` elemento Master.</span><span class="sxs-lookup"><span data-stu-id="47ed5-106">WPF gets the value of the `OrderDetails` property - a collection D of all the `Detail` items whose `OrderID` matches the `OrderID` of the master item.</span></span> <span data-ttu-id="47ed5-107">La modifica del comportamento si verifica quando si modifica la chiave primaria `OrderID` dell'elemento Master.</span><span class="sxs-lookup"><span data-stu-id="47ed5-107">The behavior change arises when you change the primary key `OrderID` of the master item.</span></span> <span data-ttu-id="47ed5-108">ADO modifica automaticamente l'`OrderID` di ognuno dei record interessati nella raccolta dei dettagli, vale a dire quelli copiati nella raccolta D.</span><span class="sxs-lookup"><span data-stu-id="47ed5-108">ADO automatically changes the `OrderID` of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="47ed5-109">Cosa accade a D?</span><span class="sxs-lookup"><span data-stu-id="47ed5-109">But what happens to D?</span></span>

- <span data-ttu-id="47ed5-110">Comportamento precedente: la raccolta D è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="47ed5-110">Old behavior: Collection D is cleared.</span></span> <span data-ttu-id="47ed5-111">L'elemento master *non* genera una notifica della modifica per la proprietà `OrderDetails`.</span><span class="sxs-lookup"><span data-stu-id="47ed5-111">The master item does *not* raise a change notification for property `OrderDetails`.</span></span> <span data-ttu-id="47ed5-112">L'oggetto ListBox continua a usare la raccolta D, che ora è vuota.</span><span class="sxs-lookup"><span data-stu-id="47ed5-112">The ListBox continues to use collection D, which is now empty.</span></span>
- <span data-ttu-id="47ed5-113">Nuovo comportamento: la raccolta D rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="47ed5-113">New behavior:  Collection D is unchanged.</span></span> <span data-ttu-id="47ed5-114">Ognuno dei relativi elementi genera una notifica della modifica della proprietà `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="47ed5-114">Each of its items raises a change notification for the `OrderID` property.</span></span> <span data-ttu-id="47ed5-115">L'oggetto ListBox continua a usare la raccolta D e visualizza i dettagli con il nuovo `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="47ed5-115">The ListBox continues to use collection D, and displays the details with the new `OrderID`.</span></span> <span data-ttu-id="47ed5-116">WPF implementa il nuovo comportamento creando la raccolta D in un modo diverso: chiamando il metodo ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> con l'argomento `followParent` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="47ed5-116">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the `followParent` argument set to `true`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47ed5-117">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="47ed5-117">Suggestion</span></span>

<span data-ttu-id="47ed5-118">Per ottenere il nuovo comportamento, le app usano l'opzione AppContext.</span><span class="sxs-lookup"><span data-stu-id="47ed5-118">An app gets the new behavior by using the following AppContext switch.</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

<span data-ttu-id="47ed5-119">Per impostazione predefinita, l'opzione è impostata su `true` (comportamento precedente) per le app destinate a .NET 4.7.1 o versione precedente, e su `false` (nuovo comportamento) per le app destinate a .NET 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="47ed5-119">The switch defaults to `true` (old behavior) for apps that target .NET 4.7.1 or below, and to `false` (new behavior) for apps that target .NET 4.7.2 or above.</span></span>

| <span data-ttu-id="47ed5-120">Nome</span><span class="sxs-lookup"><span data-stu-id="47ed5-120">Name</span></span>    | <span data-ttu-id="47ed5-121">Valore</span><span class="sxs-lookup"><span data-stu-id="47ed5-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47ed5-122">Scope</span><span class="sxs-lookup"><span data-stu-id="47ed5-122">Scope</span></span>   | <span data-ttu-id="47ed5-123">Minorenne</span><span class="sxs-lookup"><span data-stu-id="47ed5-123">Minor</span></span>       |
| <span data-ttu-id="47ed5-124">Version</span><span class="sxs-lookup"><span data-stu-id="47ed5-124">Version</span></span> | <span data-ttu-id="47ed5-125">4.7.2</span><span class="sxs-lookup"><span data-stu-id="47ed5-125">4.7.2</span></span>       |
| <span data-ttu-id="47ed5-126">Type</span><span class="sxs-lookup"><span data-stu-id="47ed5-126">Type</span></span>    | <span data-ttu-id="47ed5-127">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="47ed5-127">Retargeting</span></span> |
