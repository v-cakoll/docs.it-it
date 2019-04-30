---
title: 'Procedura: Creare ed eseguire il binding a una classe ObservableCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 45f8b097bfdb8d3d7994e53ea05146aa6de0fc21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020920"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a><span data-ttu-id="d5479-102">Procedura: Creare ed eseguire il binding a una classe ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="d5479-102">How to: Create and Bind to an ObservableCollection</span></span>
<span data-ttu-id="d5479-103">Questo esempio illustra come creare e associare a una raccolta da cui deriva il <xref:System.Collections.ObjectModel.ObservableCollection%601> (classe), che è una classe collection che fornisce notifiche in caso di aggiunta o rimozione di elementi.</span><span class="sxs-lookup"><span data-stu-id="d5479-103">This example shows how to create and bind to a collection that derives from the <xref:System.Collections.ObjectModel.ObservableCollection%601> class, which is a collection class that provides notifications when items get added or removed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5479-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5479-104">Example</span></span>  
 <span data-ttu-id="d5479-105">L'esempio seguente illustra l'implementazione di una raccolta `NameList`:</span><span class="sxs-lookup"><span data-stu-id="d5479-105">The following example shows the implementation of a `NameList` collection:</span></span>  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 <span data-ttu-id="d5479-106">È possibile rendere la raccolta disponibile per il binding in modo analogo ad altri oggetti [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], come descritto in [Rendere i dati disponibili per l'associazione in XAML](how-to-make-data-available-for-binding-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d5479-106">You can make the collection available for binding the same way you would with other [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects, as described in [Make Data Available for Binding in XAML](how-to-make-data-available-for-binding-in-xaml.md).</span></span> <span data-ttu-id="d5479-107">Ad esempio, è possibile creare un'istanza della raccolta in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e specificare la raccolta come risorsa, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d5479-107">For example, you can instantiate the collection in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and specify the collection as a resource, as shown here:</span></span>  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 <span data-ttu-id="d5479-108">Sarà quindi possibile eseguire il binding alla raccolta:</span><span class="sxs-lookup"><span data-stu-id="d5479-108">You can then bind to the collection:</span></span>  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 <span data-ttu-id="d5479-109">La definizione di `NameItemTemplate` non viene mostrata qui.</span><span class="sxs-lookup"><span data-stu-id="d5479-109">The definition of `NameItemTemplate` is not shown here.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5479-110">Gli oggetti nella raccolta devono soddisfare i requisiti descritti in [Cenni preliminari sulle origini del binding](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5479-110">The objects in your collection must satisfy the requirements described in the [Binding Sources Overview](binding-sources-overview.md).</span></span> <span data-ttu-id="d5479-111">In particolare, se si usa <xref:System.Windows.Data.BindingMode.OneWay> oppure <xref:System.Windows.Data.BindingMode.TwoWay> (ad esempio, è necessario il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aggiornare quando le proprietà di origine cambiano in modo dinamico), è necessario implementare un meccanismo di notifica adeguato per le proprietà modificata, ad esempio il <xref:System.ComponentModel.INotifyPropertyChanged>dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d5479-111">In particular, if you are using <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> (for example, you want your [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to update when the source properties change dynamically), you must implement a suitable property changed notification mechanism such as the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span>  
  
 <span data-ttu-id="d5479-112">Per altre informazioni, vedere la sezione Associazione alle raccolte in [Panoramica sul data binding](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5479-112">For more information, see the Binding to Collections section in the [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5479-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5479-113">See also</span></span>

- [<span data-ttu-id="d5479-114">Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="d5479-114">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="d5479-115">Filtrare i dati di una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="d5479-115">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="d5479-116">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="d5479-116">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="d5479-117">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="d5479-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="d5479-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d5479-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
