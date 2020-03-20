---
title: Implementazione della logica di business (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: 51b92549a40d0e5121cc390f5dbdf726cc06404b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174550"
---
# <a name="implementing-business-logic-linq-to-sql"></a><span data-ttu-id="4e66a-102">Implementazione della logica di business (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="4e66a-102">Implementing Business Logic (LINQ to SQL)</span></span>
<span data-ttu-id="4e66a-103">Il termine "regola business" in questo argomento si riferisce a qualsiasi regola personalizzata o test di convalida applicato ai dati prima che vengano inseriti, aggiornati o eliminati dal database.</span><span class="sxs-lookup"><span data-stu-id="4e66a-103">The term "business logic" in this topic refers to any custom rules or validation tests that you apply to data before it is inserted, updated or deleted from the database.</span></span> <span data-ttu-id="4e66a-104">La regola business viene talvolta definita anche "regola dominio".</span><span class="sxs-lookup"><span data-stu-id="4e66a-104">Business logic is also sometimes referred to as "business rules" or "domain logic."</span></span> <span data-ttu-id="4e66a-105">Nelle applicazioni a più livelli viene in genere progettata come livello logico in modo da essere modificata indipendentemente dal livello di presentazione o dal livello di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="4e66a-105">In n-tier applications it is typically designed as a logical layer so that it can be modified independently of the presentation layer or data access layer.</span></span> <span data-ttu-id="4e66a-106">La logica di business può essere richiamata dal livello di accesso ai dati prima o dopo l'aggiornamento, l'inserimento o l'eliminazione dei dati dal database.</span><span class="sxs-lookup"><span data-stu-id="4e66a-106">The business logic can be invoked by the data access layer before or after any update, insertion, or deletion of data in the database.</span></span>  
  
 <span data-ttu-id="4e66a-107">La regola business è semplice quanto la convalida di uno schema per assicurarsi che il tipo del campo sia compatibile con il tipo della colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="4e66a-107">The business logic can be as simple as a schema validation to make sure that the type of the field is compatible with the type of the table column.</span></span> <span data-ttu-id="4e66a-108">Oppure può essere costituita da un set di oggetti che interagiscono in modalità arbitrariamente complesse.</span><span class="sxs-lookup"><span data-stu-id="4e66a-108">Or it can consist of a set of objects that interact in arbitrarily complex ways.</span></span> <span data-ttu-id="4e66a-109">Le regole possono essere implementate come stored procedure nel database o come oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="4e66a-109">The rules may be implemented as stored procedures on the database or as in-memory objects.</span></span> <span data-ttu-id="4e66a-110">Tuttavia, la logica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di business viene implementata, consente di utilizzare classi parziali e metodi parziali per separare la logica di business dal codice di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="4e66a-110">However the business logic is implemented, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] enables you use partial classes and partial methods to separate the business logic from the data access code.</span></span>  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a><span data-ttu-id="4e66a-111">Richiamo della regola business da LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4e66a-111">How LINQ to SQL Invokes Your Business Logic</span></span>  
 <span data-ttu-id="4e66a-112">Quando si genera una classe di entità in fase di progettazione, manualmente o tramite Object Relational Designer o SQLMetal, viene definita come classe parziale.</span><span class="sxs-lookup"><span data-stu-id="4e66a-112">When you generate an entity class at design time, either manually or by using the Object Relational Designer or SQLMetal, it is defined as a partial class.</span></span> <span data-ttu-id="4e66a-113">Ciò significa che, in un file di codice separato, è possibile definire un'altra parte della classe di entità contenente la regola business personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4e66a-113">This means that, in a separate code file, you can define another part of the entity class that contains your custom business logic.</span></span> <span data-ttu-id="4e66a-114">In fase di compilazione le due parti vengono unite in un'unica classe.</span><span class="sxs-lookup"><span data-stu-id="4e66a-114">At compile time, the two parts are merged into a single class.</span></span> <span data-ttu-id="4e66a-115">Tuttavia, se è necessario rigenerare le classi di entità utilizzando Object Relational Designer o SQLMetal, è possibile farlo e la parte della classe non verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="4e66a-115">But if you have to regenerate your entity classes by using the Object Relational Designer or SQLMetal, you can do so and your part of the class will not be modified.</span></span>  
  
 <span data-ttu-id="4e66a-116">Le classi parziali che definiscono le entità e <xref:System.Data.Linq.DataContext> contengono metodi parziali.</span><span class="sxs-lookup"><span data-stu-id="4e66a-116">The partial classes that define entities and the <xref:System.Data.Linq.DataContext> contain partial methods.</span></span> <span data-ttu-id="4e66a-117">Si tratta di punti di estensibilità che è possibile usare per applicare la regola business prima e dopo un aggiornamento, inserimento o eliminazione di un'entità o di una proprietà dell'entità.</span><span class="sxs-lookup"><span data-stu-id="4e66a-117">These are the extensibility points that you can use to apply your business logic before and after any update, insert, or delete for an entity or entity property.</span></span> <span data-ttu-id="4e66a-118">È possibile considerare i metodi parziali come eventi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4e66a-118">Partial methods can be thought of as compile-time events.</span></span> <span data-ttu-id="4e66a-119">Il generatore di codice definisce una firma del metodo e chiama i metodi nelle funzioni di accesso alle proprietà get e set nonché il costruttore `DataContext`, e in alcuni casi automaticamente quando viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e66a-119">The code-generator defines a method signature and calls the methods in the get and set property accessors, the `DataContext` constructor, and in some cases behind the scenes when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="4e66a-120">Tuttavia, se non si implementa un particolare metodo parziale, tutti i riferimenti relativi e la definizione verranno rimossi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4e66a-120">However, if you do not implement a particular partial method, then all the references to it and the definition are removed at compile time.</span></span>  
  
 <span data-ttu-id="4e66a-121">Nella definizione di implementazione scritta nel file di codice separato, è possibile eseguire la regola personalizzata necessaria.</span><span class="sxs-lookup"><span data-stu-id="4e66a-121">In the implementing definition that you write in your separate code file, you can perform whatever custom logic is required.</span></span> <span data-ttu-id="4e66a-122">È possibile usare la classe parziale personalizzata come livello del dominio oppure è possibile chiamare dalla definizione di implementazione del metodo parziale in uno o più oggetti separati.</span><span class="sxs-lookup"><span data-stu-id="4e66a-122">You can use your partial class itself as your domain layer, or you can call from your implementing definition of the partial method into a separate object or objects.</span></span> <span data-ttu-id="4e66a-123">In entrambi i casi, la regola business viene nettamente separata dal codice di accesso ai dati e dal codice del livello di presentazione.</span><span class="sxs-lookup"><span data-stu-id="4e66a-123">Either way, your business logic is cleanly separated from both your data access code and your presentation layer code.</span></span>  
  
## <a name="a-closer-look-at-the-extensibility-points"></a><span data-ttu-id="4e66a-124">Informazioni dettagliate sui punti di estensibilità</span><span class="sxs-lookup"><span data-stu-id="4e66a-124">A Closer Look at the Extensibility Points</span></span>  
 <span data-ttu-id="4e66a-125">Nell'esempio seguente viene illustrata una parte del `DataContext` codice generato da `Customers` `Orders`Object Relational Designer per la classe che dispone di due tabelle: e .</span><span class="sxs-lookup"><span data-stu-id="4e66a-125">The following example shows part of the code generated by the Object Relational Designer for the `DataContext` class that has two tables: `Customers` and `Orders`.</span></span> <span data-ttu-id="4e66a-126">Tenere presente che i metodi di inserimento, aggiornamento ed eliminazione vengono definiti per ogni tabella della classe.</span><span class="sxs-lookup"><span data-stu-id="4e66a-126">Note that Insert, Update, and Delete methods are defined for each table in the class.</span></span>  
  
```vb  
Partial Public Class Northwnd  
    Inherits System.Data.Linq.DataContext  
  
    Private Shared mappingSource As _  
        System.Data.Linq.Mapping.MappingSource = New _  
        AttributeMappingSource  
  
    #Region "Extensibility Method Definitions"  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub InsertCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub UpdateCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub DeleteCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub InsertOrder(instance As [Order])  
    End Sub  
    Partial Private Sub UpdateOrder(instance As [Order])  
    End Sub  
    Partial Private Sub DeleteOrder(instance As [Order])  
    End Sub  
    #End Region  
```  
  
```csharp  
public partial class MyNorthWindDataContext : System.Data.Linq.DataContext  
    {  
        private static System.Data.Linq.Mapping.MappingSource mappingSource = new AttributeMappingSource();  
  
        #region Extensibility Method Definitions  
        partial void OnCreated();  
        partial void InsertCustomer(Customer instance);  
        partial void UpdateCustomer(Customer instance);  
        partial void DeleteCustomer(Customer instance);  
        partial void InsertOrder(Order instance);  
        partial void UpdateOrder(Order instance);  
        partial void DeleteOrder(Order instance);  
        #endregion  
```  
  
 <span data-ttu-id="4e66a-127">Se si implementano i metodi di inserimento, aggiornamento ed eliminazione nella classe parziale, il runtime [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] chiamerà tali metodi anziché i metodi predefiniti personalizzati quando viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e66a-127">If you implement the Insert, Update and Delete methods in your partial class, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime will call them instead of its own default methods when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="4e66a-128">In questo modo è possibile eseguire l'override del comportamento predefinito per le operazioni di creazione, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="4e66a-128">This enables you to override the default behavior for create / read / update / delete operations.</span></span> <span data-ttu-id="4e66a-129">Per ulteriori informazioni, vedere [Procedura dettagliata: personalizzazione del comportamento di inserimento, aggiornamento ed eliminazione delle classi di entità](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span><span class="sxs-lookup"><span data-stu-id="4e66a-129">For more information, see [Walkthrough: Customizing the insert, update, and delete behavior of entity classes](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span></span>  
  
 <span data-ttu-id="4e66a-130">Il metodo `OnCreated` viene chiamato nel costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="4e66a-130">The `OnCreated` method is called in the class constructor.</span></span>  
  
```vb  
Public Sub New(ByVal connection As String)  
    MyBase.New(connection, mappingSource)  
    OnCreated()  
End Sub  
```  
  
```csharp  
public MyNorthWindDataContext(string connection) :  
            base(connection, mappingSource)  
        {  
            OnCreated();  
        }  
```  
  
 <span data-ttu-id="4e66a-131">Per le classi di entità sono disponibili tre metodi che vengono chiamati dal runtime [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] quando l'entità viene creata, caricata e convalidata (quando viene chiamato `SubmitChanges`).</span><span class="sxs-lookup"><span data-stu-id="4e66a-131">The entity classes have three methods that are called by the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime when the entity is created, loaded, and validated (when `SubmitChanges` is called).</span></span> <span data-ttu-id="4e66a-132">Le classi di entità dispongono inoltre di due metodi parziali per ogni proprietà, uno chiamato prima dell'impostazione della proprietà e l'altro dopo.</span><span class="sxs-lookup"><span data-stu-id="4e66a-132">The entity classes also have two partial methods for each property, one that is called before the property is set, and one that is called after.</span></span> <span data-ttu-id="4e66a-133">Nell'esempio di codice seguente vengono illustrati alcuni metodi generati per la classe `Customer`:</span><span class="sxs-lookup"><span data-stu-id="4e66a-133">The following code example shows some of the methods generated for the `Customer` class:</span></span>  
  
```vb  
#Region "Extensibility Method Definitions"  
    Partial Private Sub OnLoaded()  
    End Sub  
    Partial Private Sub OnValidate(action As _  
        System.Data.Linq.ChangeAction)  
    End Sub  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub OnCustomerIDChanging(value As String)  
    End Sub  
    Partial Private Sub OnCustomerIDChanged()  
    End Sub  
    Partial Private Sub OnCompanyNameChanging(value As String)  
    End Sub  
    Partial Private Sub OnCompanyNameChanged()  
    End Sub  
' ...Additional Changing/Changed methods for each property.  
```  
  
```csharp  
#region Extensibility Method Definitions  
    partial void OnLoaded();  
    partial void OnValidate();  
    partial void OnCreated();  
    partial void OnCustomerIDChanging(string value);  
    partial void OnCustomerIDChanged();  
    partial void OnCompanyNameChanging(string value);  
    partial void OnCompanyNameChanged();  
// ...additional Changing/Changed methods for each property  
```  
  
 <span data-ttu-id="4e66a-134">I metodi vengono chiamati nella funzione di accesso set della proprietà come illustrato nell'esempio seguente per la proprietà `CustomerID`:</span><span class="sxs-lookup"><span data-stu-id="4e66a-134">The methods are called in the property set accessor as shown in the following example for the `CustomerID` property:</span></span>  
  
```vb  
Public Property CustomerID() As String  
    Set  
        If (String.Equals(Me._CustomerID, value) = False) Then  
            Me.OnCustomerIDChanging(value)  
            Me.SendPropertyChanging()  
            Me._CustomerID = value  
            Me.SendPropertyChanged("CustomerID")  
            Me.OnCustomerIDChanged()  
        End If  
    End Set  
End Property  
```  
  
```csharp  
public string CustomerID  
{  
    set  
    {  
        if ((this._CustomerID != value))  
        {  
            this.OnCustomerIDChanging(value);  
            this.SendPropertyChanging();  
            this._CustomerID = value;  
            this.SendPropertyChanged("CustomerID");  
            this.OnCustomerIDChanged();  
        }  
     }  
}  
```  
  
 <span data-ttu-id="4e66a-135">Nella parte personalizzata della classe, scrivere una definizione di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4e66a-135">In your part of the class, you write an implementing definition of the method.</span></span> <span data-ttu-id="4e66a-136">In Visual Studio, `partial` dopo aver digitato IntelliSense per le definizioni di metodo nell'altra parte della classe.</span><span class="sxs-lookup"><span data-stu-id="4e66a-136">In Visual Studio, after you type `partial` you will see IntelliSense for the method definitions in the other part of the class.</span></span>  
  
```vb  
Partial Public Class Customer  
    Private Sub OnCustomerIDChanging(value As String)  
        ' Perform custom validation logic here.  
    End Sub  
End Class  
```  
  
```csharp  
partial class Customer
    {  
        partial void OnCustomerIDChanging(string value)  
        {  
            //Perform custom validation logic here.  
        }  
    }  
```  
  
 <span data-ttu-id="4e66a-137">Per altre informazioni su come aggiungere la regola business all'applicazione usando i metodi parziali, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e66a-137">For more information about how to add business logic to your application by using partial methods, see the following topics:</span></span>  
  
 [<span data-ttu-id="4e66a-138">Procedura: Aggiungere la convalida a classi di entità</span><span class="sxs-lookup"><span data-stu-id="4e66a-138">How to: Add validation to entity classes</span></span>](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [<span data-ttu-id="4e66a-139">Procedura dettagliata: personalizzazione del comportamento di inserimento, aggiornamento ed eliminazione delle classi di entità</span><span class="sxs-lookup"><span data-stu-id="4e66a-139">Walkthrough: Customizing the insert, update, and delete behavior of entity classes</span></span>](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 <span data-ttu-id="4e66a-140">[Procedura dettagliata: Aggiunta della convalida a classi di entità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="4e66a-140">[Walkthrough: Adding Validation to Entity Classes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e66a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e66a-141">See also</span></span>

- [<span data-ttu-id="4e66a-142">Classi e metodi parziali</span><span class="sxs-lookup"><span data-stu-id="4e66a-142">Partial Classes and Methods</span></span>](../../../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [<span data-ttu-id="4e66a-143">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="4e66a-143">Partial Methods</span></span>](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [<span data-ttu-id="4e66a-144">Strumenti LINQ to SQL in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4e66a-144">LINQ to SQL Tools in Visual Studio</span></span>](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [<span data-ttu-id="4e66a-145">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="4e66a-145">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
