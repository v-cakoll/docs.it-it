---
title: 'Procedura: Applicare attributi nei controlli Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922788"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Procedura: Applicare attributi nei controlli Windows Forms
Per sviluppare componenti e controlli che interagiscono correttamente con l'ambiente di progettazione e vengono eseguiti correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi a classi e membri.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi in un controllo personalizzato. Il controllo illustra una semplice funzionalità di registrazione. Quando il controllo è associato a un'origine dati, Visualizza i valori inviati dall'origine dati in un <xref:System.Windows.Forms.DataGridView> controllo. Se un valore supera il valore specificato dalla `Threshold` proprietà, viene generato un `ThresholdExceeded` evento.  
  
 Registra i valori con una `LogEntry` classe. `AttributesDemoControl` La `LogEntry` classe è una classe modello, che significa che è parametrizzata sul tipo che registra. Se, ad esempio, `AttributesDemoControl` l'oggetto sta registrando `float`valori di `LogEntry` tipo, ogni istanza viene dichiarata e utilizzata come indicato di seguito.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Poiché `LogEntry` è parametrizzato da un tipo arbitrario, deve utilizzare la reflection per operare sul tipo di parametro. Per il funzionamento della funzionalità di soglia, il tipo `T` di parametro deve <xref:System.IComparable> implementare l'interfaccia.  
  
 Il form che ospita le `AttributesDemoControl` query di un contatore delle prestazioni periodicamente. Ogni valore è incluso in un oggetto `LogEntry` del tipo appropriato e viene aggiunto al <xref:System.Windows.Forms.BindingSource>form. Riceve il valore tramite la relativa data binding e visualizza il valore in un <xref:System.Windows.Forms.DataGridView> controllo. `AttributesDemoControl`  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Il primo esempio di codice è `AttributesDemoControl` l'implementazione di. Nel secondo esempio di codice viene illustrato un form che `AttributesDemoControl`utilizza.  
  
## <a name="class-level-attributes"></a>Attributi a livello di classe  
 Alcuni attributi vengono applicati a livello di classe. Nell'esempio di codice riportato di seguito vengono illustrati gli attributi comunemente applicati a un controllo Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter (attributo)  
 <xref:System.ComponentModel.TypeConverterAttribute>è un altro attributo a livello di classe comunemente utilizzato. Nell'esempio di codice riportato di seguito viene illustrato `LogEntry` l'utilizzo della classe. <xref:System.ComponentModel.TypeConverter> In questo esempio viene inoltre illustrata un'implementazione di `LogEntry` per il tipo `LogEntryTypeConverter`, denominato.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attributi a livello di membro  
 Alcuni attributi vengono applicati a livello di membro. Negli esempi di codice riportati di seguito vengono illustrati alcuni attributi che vengono comunemente applicati alle proprietà dei controlli Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Attributo AmbientValue  
 Nell'esempio seguente viene illustrato <xref:System.ComponentModel.AmbientValueAttribute> il e viene mostrato il codice che supporta l'interazione con l'ambiente di progettazione. Questa interazione è detta *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Attributi DataBinding  
 Negli esempi seguenti viene illustrata un'implementazione di data binding complesse. Il livello <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>di classe, illustrato in precedenza, specifica `DataSource` le `DataMember` proprietà e da utilizzare per data binding. Specifica il tipo a cui la `DataSource` proprietà eseguirà l'associazione. <xref:System.ComponentModel.AttributeProviderAttribute>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Il form che ospita l' `AttributesDemoControl` oggetto richiede un riferimento `AttributesDemoControl` all'assembly per la compilazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Attributi nei controlli Windows Forms](attributes-in-windows-forms-controls.md)
- [Procedura: Serializzare raccolte di tipi standard con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
