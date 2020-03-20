---
title: Argomenti obbligatori e gruppi di overload
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: 4eb62306f52b8ff890d5a5333c3789bd84ad7f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142940"
---
# <a name="required-arguments-and-overload-groups"></a><span data-ttu-id="10732-102">Argomenti obbligatori e gruppi di overload</span><span class="sxs-lookup"><span data-stu-id="10732-102">Required Arguments and Overload Groups</span></span>
<span data-ttu-id="10732-103">Le attività possono essere configurate in modo che venga richiesta l'associazione di determinati argomenti affinché l'attività risulti valida per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="10732-103">Activities can be configured so that certain arguments are required to be bound for the activity to be valid for execution.</span></span> <span data-ttu-id="10732-104">L'attributo `RequiredArgument` viene usato per indicare che determinati argomenti di un'attività sono obbligatori mentre l'attributo `OverloadGroup` viene usato per raggruppare insieme categorie di argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="10732-104">The `RequiredArgument` attribute is used to indicate that certain arguments on an activity are required and the `OverloadGroup` attribute is used to group categories of required arguments together.</span></span> <span data-ttu-id="10732-105">Tramite gli attributi, gli autori dell'attività possono fornire configurazioni di convalida di attività semplici o complesse.</span><span class="sxs-lookup"><span data-stu-id="10732-105">By using the attributes, activity authors can provide simple or complex activity validation configurations.</span></span>  
  
## <a name="using-required-arguments"></a><span data-ttu-id="10732-106">Uso di argomenti obbligatori</span><span class="sxs-lookup"><span data-stu-id="10732-106">Using Required Arguments</span></span>  
 <span data-ttu-id="10732-107">Per usare l'attributo `RequiredArgument` in un'attività, indicare gli argomenti desiderati usando l'oggetto <xref:System.Activities.RequiredArgumentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10732-107">To use the `RequiredArgument` attribute in an activity, indicate the desired arguments using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="10732-108">In questo esempio viene definita un'attività `Add` che dispone di due argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="10732-108">In this example, an `Add` activity is defined that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="10732-109">In XAML gli argomenti obbligatori vengono indicati anche tramite l'oggetto <xref:System.Activities.RequiredArgumentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10732-109">In XAML, required arguments are also indicated by using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="10732-110">In questo esempio l'attività `Add` viene definita tramite tre argomenti e viene usata un'attività <xref:System.Activities.Statements.Assign%601> per eseguire l'operazione di aggiunta.</span><span class="sxs-lookup"><span data-stu-id="10732-110">In this example the `Add` activity is defined by using three arguments and uses an <xref:System.Activities.Statements.Assign%601> activity to perform the add operation.</span></span>  
  
```xaml  
<Activity x:Class="ValidationDemo.Add" ...>  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Result" Type="OutArgument(x:Int32)" />  
  </x:Members>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[Result]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[Operand1 + Operand2]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Activity>  
```  
  
 <span data-ttu-id="10732-111">Se viene usata l'attività e nessuno degli argomenti obbligatori viene associato, viene restituito il seguente errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="10732-111">If the activity is used and either of the required arguments is not bound the following validation error is returned.</span></span>  
  
 <span data-ttu-id="10732-112">**Valore non specificato per un argomento di attività 'Operand1' obbligatorio.**</span><span class="sxs-lookup"><span data-stu-id="10732-112">**Value for a required activity argument 'Operand1' was not supplied.**</span></span>  
> [!NOTE]
> <span data-ttu-id="10732-113">Per ulteriori informazioni sul controllo e la gestione di errori e avvisi di convalida, vedere Richiamare la [convalida dell'attività](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="10732-113">For more information about checking for and handling validation errors and warnings, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
## <a name="using-overload-groups"></a><span data-ttu-id="10732-114">Uso di gruppi di overload</span><span class="sxs-lookup"><span data-stu-id="10732-114">Using Overload Groups</span></span>

<span data-ttu-id="10732-115">I gruppi di overload offrono un metodo per indicare le combinazioni di argomenti valide in un'attività.</span><span class="sxs-lookup"><span data-stu-id="10732-115">Overload groups provide a method for indicating which combinations of arguments are valid in an activity.</span></span> <span data-ttu-id="10732-116">Gli argomenti vengono raggruppati insieme tramite l'oggetto <xref:System.Activities.OverloadGroupAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10732-116">Arguments are grouped together by using <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="10732-117">A ogni gruppo viene assegnato un <xref:System.Activities.OverloadGroupAttribute>nome specificato dal metodo .</span><span class="sxs-lookup"><span data-stu-id="10732-117">Each group is given a name that is specified by the <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="10732-118">L'attività è valida quando viene associato un solo set di argomenti in un gruppo di overload.</span><span class="sxs-lookup"><span data-stu-id="10732-118">The activity is valid when only one set of arguments in an overload group are bound.</span></span> <span data-ttu-id="10732-119">Nell'esempio seguente viene definita una classe `CreateLocation`.</span><span class="sxs-lookup"><span data-stu-id="10732-119">In the following example, a `CreateLocation` class is defined.</span></span>  
  
```csharp  
class CreateLocation: Activity  
{  
    [RequiredArgument]  
    public InArgument<string> Name { get; set; }  
  
    public InArgument<string> Description { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Latitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Longitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    [OverloadGroup("G3")]  
    public InArgument<string> Street { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> City { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> State { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G3")]  
    public InArgument<int> Zip { get; set; }
}  
```  
  
 <span data-ttu-id="10732-120">L'obiettivo di questa attività è specificare un percorso negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="10732-120">The objective of this activity is to specify a location in the US.</span></span> <span data-ttu-id="10732-121">A questo scopo, l'utente dell'attività può specificare il percorso usando uno di tre gruppi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="10732-121">To do this, the user of the activity can specify the location using one of three groups of arguments.</span></span> <span data-ttu-id="10732-122">Per specificare le combinazioni di argomenti valide, vengono definiti tre gruppi di overload.</span><span class="sxs-lookup"><span data-stu-id="10732-122">To specify the valid combinations of arguments, three overload groups are defined.</span></span> <span data-ttu-id="10732-123">`G1` contiene gli argomenti `Latitude` e `Longitude`.</span><span class="sxs-lookup"><span data-stu-id="10732-123">`G1` contains the `Latitude` and `Longitude` arguments.</span></span> <span data-ttu-id="10732-124">`G2` contiene `Street`, `City` e `State`.</span><span class="sxs-lookup"><span data-stu-id="10732-124">`G2` contains `Street`, `City`, and `State`.</span></span> <span data-ttu-id="10732-125">`G3` contiene `Street` e `Zip`.</span><span class="sxs-lookup"><span data-stu-id="10732-125">`G3` contains `Street` and `Zip`.</span></span> <span data-ttu-id="10732-126">`Name` è anche un argomento obbligatorio, ma non fa parte di un gruppo di overload.</span><span class="sxs-lookup"><span data-stu-id="10732-126">`Name` is also a required argument, but it is not part of an overload group.</span></span> <span data-ttu-id="10732-127">Affinché questa attività sia valida, `Name` dovrebbe essere associato insieme a tutti gli argomenti di un unico gruppo di overload soltanto.</span><span class="sxs-lookup"><span data-stu-id="10732-127">For this activity to be valid, `Name` would have to be bound together with all of the arguments from one and only one overload group.</span></span>  
  
 <span data-ttu-id="10732-128">Nell'esempio seguente, tratto dall'esempio Attività di accesso `ConnectionString` al `ConfigFileSectionName` [database,](./samples/database-access-activities.md) sono disponibili due gruppi di overload: e .</span><span class="sxs-lookup"><span data-stu-id="10732-128">In the following example, taken from the [Database Access Activities](./samples/database-access-activities.md) sample, there are two overload groups: `ConnectionString` and `ConfigFileSectionName`.</span></span> <span data-ttu-id="10732-129">Perché questa attività sia valida, gli argomenti `ProviderName` e `ConnectionString` o l'argomento `ConfigName`, ma non tutti, devono essere associati.</span><span class="sxs-lookup"><span data-stu-id="10732-129">For this activity to be valid, either the `ProviderName` and `ConnectionString` arguments must be bound, or the `ConfigName` argument, but not both.</span></span>  
  
```csharp  
public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }
}  
```  
  
 <span data-ttu-id="10732-130">Quando si definisce un gruppo di overload:</span><span class="sxs-lookup"><span data-stu-id="10732-130">When defining an overload group:</span></span>  
  
- <span data-ttu-id="10732-131">Un gruppo di overload non può essere un subset o un set equivalente di un altro gruppo di overload.</span><span class="sxs-lookup"><span data-stu-id="10732-131">An overload group cannot be a subset or an equivalent set of another overload group.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="10732-132">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="10732-132">There is one exception to this rule.</span></span> <span data-ttu-id="10732-133">Se un gruppo di overload è un subset di un altro gruppo di overload e il subset contiene solo argomenti in cui `RequiredArgument` è `false`, il gruppo di overload è valido.</span><span class="sxs-lookup"><span data-stu-id="10732-133">If an overload group is a subset of another overload group, and the subset contains only arguments where `RequiredArgument` is `false`, then the overload group is valid.</span></span>  
  
- <span data-ttu-id="10732-134">I gruppi di overload possono sovrapporsi ma è un errore se l'intersezione dei gruppi contiene tutti gli argomenti obbligatori di uno o entrambi i gruppi di overload.</span><span class="sxs-lookup"><span data-stu-id="10732-134">Overload groups can overlap but it is an error if the intersection of the groups contains all the required arguments of one or both of the overload groups.</span></span> <span data-ttu-id="10732-135">Nell'esempio precedente i gruppi di overload `G2` e `G3` si sovrapponevano, ma poiché l'intersezione non conteneva tutti gli argomenti di uno o entrambi i gruppi, questa situazione era valida.</span><span class="sxs-lookup"><span data-stu-id="10732-135">In the previous example the `G2` and `G3` overload groups overlapped, but because the intersection did not contain all the arguments of one or both of the groups this was valid.</span></span>  
  
 <span data-ttu-id="10732-136">Quando si associano gli argomenti in un gruppo di overload:</span><span class="sxs-lookup"><span data-stu-id="10732-136">When binding arguments in an overload group:</span></span>  
  
- <span data-ttu-id="10732-137">Un gruppo di overload è considerato associato se vengono associati tutti gli argomenti `RequiredArgument` nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="10732-137">An overload group is considered bound if all the `RequiredArgument` arguments in the group are bound.</span></span>  
  
- <span data-ttu-id="10732-138">Se un gruppo dispone di zero argomenti `RequiredArgument` e almeno un argomento associato, tale gruppo è considerato associato.</span><span class="sxs-lookup"><span data-stu-id="10732-138">If a group has zero `RequiredArgument` arguments and at least one argument bound, then the group is considered bound.</span></span>  
  
- <span data-ttu-id="10732-139">Si verifica un errore di convalida se nessun gruppo di overload è associato, a meno che un gruppo di overload non presenti all'interno alcun argomento `RequiredArgument`.</span><span class="sxs-lookup"><span data-stu-id="10732-139">It is a validation error if no overload groups are bound unless one overload group has no `RequiredArgument` arguments in it.</span></span>  
  
- <span data-ttu-id="10732-140">È un errore disporre di più gruppi di overload associati, ovvero, vengono associati tutti gli argomenti obbligatori in un gruppo di overload e viene associato anche qualsiasi argomento in un altro gruppo di overload.</span><span class="sxs-lookup"><span data-stu-id="10732-140">It is an error to have more than one overload group bound, that is, all required arguments in one overload group are bound and any argument in another overload group is also bound.</span></span>
