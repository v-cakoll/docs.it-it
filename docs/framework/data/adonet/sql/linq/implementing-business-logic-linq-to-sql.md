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
# <a name="implementing-business-logic-linq-to-sql"></a>Implementazione della logica di business (LINQ to SQL)
Il termine "regola business" in questo argomento si riferisce a qualsiasi regola personalizzata o test di convalida applicato ai dati prima che vengano inseriti, aggiornati o eliminati dal database. La regola business viene talvolta definita anche "regola dominio". Nelle applicazioni a più livelli viene in genere progettata come livello logico in modo da essere modificata indipendentemente dal livello di presentazione o dal livello di accesso ai dati. La logica di business può essere richiamata dal livello di accesso ai dati prima o dopo l'aggiornamento, l'inserimento o l'eliminazione dei dati dal database.  
  
 La regola business è semplice quanto la convalida di uno schema per assicurarsi che il tipo del campo sia compatibile con il tipo della colonna di tabella. Oppure può essere costituita da un set di oggetti che interagiscono in modalità arbitrariamente complesse. Le regole possono essere implementate come stored procedure nel database o come oggetti in memoria. Tuttavia, la logica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di business viene implementata, consente di utilizzare classi parziali e metodi parziali per separare la logica di business dal codice di accesso ai dati.  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a>Richiamo della regola business da LINQ to SQL  
 Quando si genera una classe di entità in fase di progettazione, manualmente o tramite Object Relational Designer o SQLMetal, viene definita come classe parziale. Ciò significa che, in un file di codice separato, è possibile definire un'altra parte della classe di entità contenente la regola business personalizzata. In fase di compilazione le due parti vengono unite in un'unica classe. Tuttavia, se è necessario rigenerare le classi di entità utilizzando Object Relational Designer o SQLMetal, è possibile farlo e la parte della classe non verrà modificata.  
  
 Le classi parziali che definiscono le entità e <xref:System.Data.Linq.DataContext> contengono metodi parziali. Si tratta di punti di estensibilità che è possibile usare per applicare la regola business prima e dopo un aggiornamento, inserimento o eliminazione di un'entità o di una proprietà dell'entità. È possibile considerare i metodi parziali come eventi in fase di compilazione. Il generatore di codice definisce una firma del metodo e chiama i metodi nelle funzioni di accesso alle proprietà get e set nonché il costruttore `DataContext`, e in alcuni casi automaticamente quando viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Tuttavia, se non si implementa un particolare metodo parziale, tutti i riferimenti relativi e la definizione verranno rimossi in fase di compilazione.  
  
 Nella definizione di implementazione scritta nel file di codice separato, è possibile eseguire la regola personalizzata necessaria. È possibile usare la classe parziale personalizzata come livello del dominio oppure è possibile chiamare dalla definizione di implementazione del metodo parziale in uno o più oggetti separati. In entrambi i casi, la regola business viene nettamente separata dal codice di accesso ai dati e dal codice del livello di presentazione.  
  
## <a name="a-closer-look-at-the-extensibility-points"></a>Informazioni dettagliate sui punti di estensibilità  
 Nell'esempio seguente viene illustrata una parte del `DataContext` codice generato da `Customers` `Orders`Object Relational Designer per la classe che dispone di due tabelle: e . Tenere presente che i metodi di inserimento, aggiornamento ed eliminazione vengono definiti per ogni tabella della classe.  
  
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
  
 Se si implementano i metodi di inserimento, aggiornamento ed eliminazione nella classe parziale, il runtime [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] chiamerà tali metodi anziché i metodi predefiniti personalizzati quando viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. In questo modo è possibile eseguire l'override del comportamento predefinito per le operazioni di creazione, lettura, aggiornamento ed eliminazione. Per ulteriori informazioni, vedere [Procedura dettagliata: personalizzazione del comportamento di inserimento, aggiornamento ed eliminazione delle classi di entità](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).  
  
 Il metodo `OnCreated` viene chiamato nel costruttore della classe.  
  
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
  
 Per le classi di entità sono disponibili tre metodi che vengono chiamati dal runtime [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] quando l'entità viene creata, caricata e convalidata (quando viene chiamato `SubmitChanges`). Le classi di entità dispongono inoltre di due metodi parziali per ogni proprietà, uno chiamato prima dell'impostazione della proprietà e l'altro dopo. Nell'esempio di codice seguente vengono illustrati alcuni metodi generati per la classe `Customer`:  
  
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
  
 I metodi vengono chiamati nella funzione di accesso set della proprietà come illustrato nell'esempio seguente per la proprietà `CustomerID`:  
  
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
  
 Nella parte personalizzata della classe, scrivere una definizione di implementazione del metodo. In Visual Studio, `partial` dopo aver digitato IntelliSense per le definizioni di metodo nell'altra parte della classe.  
  
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
  
 Per altre informazioni su come aggiungere la regola business all'applicazione usando i metodi parziali, vedere gli argomenti seguenti:  
  
 [Procedura: Aggiungere la convalida a classi di entità](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [Procedura dettagliata: personalizzazione del comportamento di inserimento, aggiornamento ed eliminazione delle classi di entità](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 [Procedura dettagliata: Aggiunta della convalida a classi di entità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))  
  
## <a name="see-also"></a>Vedere anche

- [Classi e metodi parziali](../../../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [Metodi parziali](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [Strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
