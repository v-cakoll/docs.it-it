---
title: 'Procedura: applicare attributi nei controlli Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 49c2aaa48a48e33a71b5112db31991975011551d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529636"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Procedura: applicare attributi nei controlli Windows Form
Per sviluppare componenti e controlli che interagiscano correttamente con l'ambiente di progettazione ed eseguire correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi alle classi e membri.  
  
## <a name="example"></a>Esempio  
 Esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi con un controllo personalizzato. Il controllo illustra una funzionalità di registrazione semplice. Quando il controllo è associato a un'origine dati, vengono visualizzati i valori inviati dall'origine dei dati in un <xref:System.Windows.Forms.DataGridView> controllo. Se un valore supera il valore specificato per il `Threshold` proprietà, un `ThresholdExceeded` viene generato l'evento.  
  
 Il `AttributesDemoControl` registra i valori con un `LogEntry` classe. La `LogEntry` classe è una classe di modello, ovvero con i parametri nel tipo che viene registrato. Ad esempio, se il `AttributesDemoControl` registra valori di tipo `float`, ogni `LogEntry` istanza viene dichiarata e utilizzata come indicato di seguito.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Poiché `LogEntry` è con parametri per un tipo arbitrario, è necessario usare la reflection per funzionare con il tipo di parametro. Per la funzionalità di lavoro, il tipo di parametro soglia `T` deve implementare il <xref:System.IComparable> interfaccia.  
  
 Il modulo che ospita il `AttributesDemoControl` esegue periodicamente una query di un contatore delle prestazioni. Ogni valore viene inserito in un `LogEntry` del tipo appropriato e aggiunto al form <xref:System.Windows.Forms.BindingSource>. Il `AttributesDemoControl` riceve il valore tramite l'associazione dati e visualizza il valore in un <xref:System.Windows.Forms.DataGridView> controllo.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Il primo esempio di codice è il `AttributesDemoControl` implementazione. Nel secondo esempio di codice viene illustrato un form che usa il `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Attributi a livello di classe  
 Alcuni attributi vengono applicati a livello di classe. Esempio di codice seguente mostra gli attributi che sono in genere applicati a un controllo Windows Form.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>Attributo TypeConverter  
 <xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe di uso comune. Esempio di codice seguente viene illustrato l'utilizzo per la `LogEntry` classe. In questo esempio viene inoltre illustrata un'implementazione di un <xref:System.ComponentModel.TypeConverter> per il `LogEntry` tipo, denominato `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attributi a livello di membro  
 Alcuni attributi vengono applicati a livello di membro. Gli esempi di codice seguenti illustrano alcuni attributi vengono in genere applicati alle proprietà dei controlli Windows Form.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Attributo AmbientValue  
 Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e il codice che supporta l'interazione con l'ambiente di progettazione. Viene chiamata per tale interazione *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Attributi di associazione dati  
 Nell'esempio seguente viene illustrata l'implementazione di data binding complesso. Il livello di classe <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, come illustrato in precedenza, specifica il `DataSource` e `DataMember` proprietà da utilizzare per l'associazione dati. Il <xref:System.ComponentModel.AttributeProviderAttribute> specifica il tipo a cui il `DataSource` assocerà la proprietà.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Il modulo che ospita il `AttributesDemoControl` richiede un riferimento al `AttributesDemoControl` assembly per eseguire la compilazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Attributi nei controlli Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [Procedura: serializzare le raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
