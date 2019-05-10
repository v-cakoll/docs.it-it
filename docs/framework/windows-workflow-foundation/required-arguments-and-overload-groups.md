---
title: Argomenti obbligatori e gruppi di overload
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: a2a5182adf34c6910f75e85505098075ffe7d3c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649324"
---
# <a name="required-arguments-and-overload-groups"></a>Argomenti obbligatori e gruppi di overload
Le attività possono essere configurate in modo che venga richiesta l'associazione di determinati argomenti affinché l'attività risulti valida per l'esecuzione. L'attributo `RequiredArgument` viene usato per indicare che determinati argomenti di un'attività sono obbligatori mentre l'attributo `OverloadGroup` viene usato per raggruppare insieme categorie di argomenti obbligatori. Tramite gli attributi, gli autori dell'attività possono fornire configurazioni di convalida di attività semplici o complesse.  
  
## <a name="using-required-arguments"></a>Uso di argomenti obbligatori  
 Per usare l'attributo `RequiredArgument` in un'attività, indicare gli argomenti desiderati usando l'oggetto <xref:System.Activities.RequiredArgumentAttribute>. In questo esempio viene definita un'attività `Add` che dispone di due argomenti obbligatori.  
  
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
  
 In XAML gli argomenti obbligatori vengono indicati anche tramite l'oggetto <xref:System.Activities.RequiredArgumentAttribute>. In questo esempio l'attività `Add` viene definita tramite tre argomenti e viene usata un'attività <xref:System.Activities.Statements.Assign%601> per eseguire l'operazione di aggiunta.  
  
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
  
 Se viene usata l'attività e nessuno degli argomenti obbligatori viene associato, viene restituito il seguente errore di convalida.  
  
 **Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand1'.**  
> [!NOTE]
> Per altre informazioni sulla ricerca e gestione di errori di convalida e avvisi, vedere [richiamo di convalida delle attività](invoking-activity-validation.md).  
  
## <a name="using-overload-groups"></a>Uso di gruppi di overload

I gruppi di overload offrono un metodo per indicare le combinazioni di argomenti valide in un'attività. Gli argomenti vengono raggruppati insieme tramite l'oggetto <xref:System.Activities.OverloadGroupAttribute>. Ogni gruppo viene assegnato un nome specificato da di <xref:System.Activities.OverloadGroupAttribute>. L'attività è valida quando sono associati un solo set di argomenti in un gruppo di overload. Nell'esempio seguente viene definita una classe `CreateLocation`.  
  
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
  
 L'obiettivo di questa attività è specificare un percorso negli Stati Uniti. A questo scopo, l'utente dell'attività può specificare il percorso usando uno di tre gruppi di argomenti. Per specificare le combinazioni di argomenti valide, vengono definiti tre gruppi di overload. `G1` contiene gli argomenti `Latitude` e `Longitude`. `G2` contiene `Street`, `City` e `State`. `G3` contiene `Street` e `Zip`. `Name` è anche un argomento obbligatorio, ma non fa parte di un gruppo di overload. Affinché questa attività sia valida, `Name` dovrebbe essere associato insieme a tutti gli argomenti di un unico gruppo di overload soltanto.  
  
 Nell'esempio seguente, estratto dal [attività di accesso al Database](./samples/database-access-activities.md) esempio, sono presenti due gruppi di overload: `ConnectionString` e `ConfigFileSectionName`. Perché questa attività sia valida, gli argomenti `ProviderName` e `ConnectionString` o l'argomento `ConfigName`, ma non tutti, devono essere associati.  
  
```  
Public class DbUpdate: AsyncCodeActivity  
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
  
 Quando si definisce un gruppo di overload:  
  
- Un gruppo di overload non può essere un subset o un set equivalente di un altro gruppo di overload.  
  
    > [!NOTE]
    >  Esiste un'eccezione a questa regola. Se un gruppo di overload è un subset di un altro gruppo di overload e il subset contiene solo argomenti in cui `RequiredArgument` è `false`, il gruppo di overload è valido.  
  
- I gruppi di overload possono sovrapporsi ma è un errore se l'intersezione dei gruppi contiene tutti gli argomenti obbligatori di uno o entrambi i gruppi di overload. Nell'esempio precedente i gruppi di overload `G2` e `G3` si sovrapponevano, ma poiché l'intersezione non conteneva tutti gli argomenti di uno o entrambi i gruppi, questa situazione era valida.  
  
 Quando si associano gli argomenti in un gruppo di overload:  
  
- Un gruppo di overload è considerato associato se vengono associati tutti gli argomenti `RequiredArgument` nel gruppo.  
  
- Se un gruppo dispone di zero argomenti `RequiredArgument` e almeno un argomento associato, tale gruppo è considerato associato.  
  
- Si verifica un errore di convalida se nessun gruppo di overload è associato, a meno che un gruppo di overload non presenti all'interno alcun argomento `RequiredArgument`.  
  
- È un errore disporre di più gruppi di overload associati, ovvero, vengono associati tutti gli argomenti obbligatori in un gruppo di overload e viene associato anche qualsiasi argomento in un altro gruppo di overload.
