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
ms.openlocfilehash: 0fd851ac413b54769bf6606b2220cf38934902be
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401434"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Procedura: Creare ed eseguire il binding a una classe ObservableCollection
In questo esempio viene illustrato come creare ed eseguire l'associazione a una raccolta che deriva <xref:System.Collections.ObjectModel.ObservableCollection%601> dalla classe, che è una classe di raccolte che fornisce notifiche quando gli elementi vengono aggiunti o rimossi.  
  
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
  
 È possibile rendere disponibile la raccolta per l'associazione in modo analogo ad altri oggetti Common Language Runtime (CLR), come descritto in [rendere i dati disponibili per l'associazione in XAML](how-to-make-data-available-for-binding-in-xaml.md). Ad esempio, è possibile creare un'istanza della raccolta in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e specificare la raccolta come risorsa, come illustrato di seguito:  
  
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
>  Gli oggetti nella raccolta devono soddisfare i requisiti descritti in [Cenni preliminari sulle origini del binding](binding-sources-overview.md). In particolare, se si utilizza <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> (ad esempio, si desidera che il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] venga aggiornato quando le proprietà di origine cambiano in modo dinamico), è necessario implementare un meccanismo di notifica appropriato modificato della <xref:System.ComponentModel.INotifyPropertyChanged>proprietà,adesempiointerfaccia.  
  
 Per altre informazioni, vedere la sezione Associazione alle raccolte in [Panoramica sul data binding](data-binding-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md)
- [Filtrare i dati di una visualizzazione](how-to-filter-data-in-a-view.md)
- [Ordinare e raggruppare dati con una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
