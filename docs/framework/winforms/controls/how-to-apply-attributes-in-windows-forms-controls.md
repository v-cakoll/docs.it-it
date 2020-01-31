---
title: Applicare gli attributi nei controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741488"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Procedura: applicare attributi nei controlli Windows Form
Per sviluppare componenti e controlli che interagiscono correttamente con l'ambiente di progettazione e vengono eseguiti correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi a classi e membri.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi in un controllo personalizzato. Il controllo illustra una semplice funzionalità di registrazione. Quando il controllo è associato a un'origine dati, Visualizza i valori inviati dall'origine dati in un controllo <xref:System.Windows.Forms.DataGridView>. Se un valore supera il valore specificato dalla proprietà `Threshold`, viene generato un evento `ThresholdExceeded`.  
  
 Il `AttributesDemoControl` registra i valori con una classe `LogEntry`. La classe `LogEntry` è una classe modello, che significa che è parametrizzata sul tipo che registra. Se, ad esempio, il `AttributesDemoControl` registra i valori di tipo `float`, ogni `LogEntry` istanza viene dichiarata e utilizzata come indicato di seguito.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Poiché `LogEntry` è parametrizzato da un tipo arbitrario, è necessario utilizzare la reflection per operare sul tipo di parametro. Per il funzionamento della funzionalità di soglia, il tipo di parametro `T` deve implementare l'interfaccia <xref:System.IComparable>.  
  
 Il modulo che ospita il `AttributesDemoControl` esegue periodicamente query su un contatore delle prestazioni. Ogni valore è incluso in un `LogEntry` del tipo appropriato e viene aggiunto al <xref:System.Windows.Forms.BindingSource>del modulo. Il `AttributesDemoControl` riceve il valore tramite la relativa data binding e visualizza il valore in un controllo di <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Il primo esempio di codice è l'implementazione del `AttributesDemoControl`. Nel secondo esempio di codice viene illustrato un modulo che utilizza il `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Attributi a livello di classe  
 Alcuni attributi vengono applicati a livello di classe. Nell'esempio di codice riportato di seguito vengono illustrati gli attributi comunemente applicati a un controllo Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter (attributo)  
 <xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe comunemente utilizzato. Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo della classe `LogEntry`. In questo esempio viene inoltre illustrata un'implementazione di un <xref:System.ComponentModel.TypeConverter> per il tipo di `LogEntry`, denominato `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attributi a livello di membro  
 Alcuni attributi vengono applicati a livello di membro. Negli esempi di codice riportati di seguito vengono illustrati alcuni attributi che vengono comunemente applicati alle proprietà dei controlli Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Attributo AmbientValue  
 Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e viene mostrato il codice che supporta l'interazione con l'ambiente di progettazione. Questa interazione è detta *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Attributi DataBinding  
 Negli esempi seguenti viene illustrata un'implementazione di data binding complesse. Il <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>a livello di classe, illustrato in precedenza, specifica le proprietà `DataSource` e `DataMember` da utilizzare per data binding. Il <xref:System.ComponentModel.AttributeProviderAttribute> specifica il tipo a cui viene associata la proprietà `DataSource`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Il form che ospita il `AttributesDemoControl` richiede un riferimento all'assembly `AttributesDemoControl` per la compilazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Attributi nei controlli Windows Form](attributes-in-windows-forms-controls.md)
- [Procedura: serializzare raccolte di tipi standard con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
