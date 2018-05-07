---
title: "Procedura: creare ed eseguire l'associazione a una classe ObservableCollection"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 5e04aa1a1d209074dbdadcb1df089e31efa84ded
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Procedura: creare ed eseguire l'associazione a una classe ObservableCollection
In questo esempio viene illustrato come creare e associare a una raccolta da cui deriva il <xref:System.Collections.ObjectModel.ObservableCollection%601> (classe), che è una classe collection che fornisce notifiche quando l'aggiunta o rimozione di elementi.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'implementazione di una raccolta `NameList`:  
  
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
  
 È possibile rendere la raccolta disponibile per il binding in modo analogo ad altri oggetti [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], come descritto in [Rendere i dati disponibili per l'associazione in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md). Ad esempio, è possibile creare un'istanza della raccolta in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e specificare la raccolta come risorsa, come illustrato di seguito:  
  
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
  
 Sarà quindi possibile eseguire il binding alla raccolta:  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 La definizione di `NameItemTemplate` non viene mostrata qui.  
  
> [!NOTE]
>  Gli oggetti nella raccolta devono soddisfare i requisiti descritti in [Cenni preliminari sulle origini del binding](../../../../docs/framework/wpf/data/binding-sources-overview.md). In particolare, se si utilizza <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> (ad esempio, è necessario il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aggiornare quando le proprietà dell'origine modificata in modo dinamico), è necessario implementare un meccanismo di notifica adeguato per le proprietà modificata, ad esempio il <xref:System.ComponentModel.INotifyPropertyChanged>interfaccia.  
  
 Per altre informazioni, vedere la sezione Associazione alle raccolte in [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Ordinare i dati in una visualizzazione](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Filtrare i dati di una visualizzazione](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Ordinare e raggruppare dati con una visualizzazione in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
