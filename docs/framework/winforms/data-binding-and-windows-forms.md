---
title: Data binding
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- data [Windows Forms], data binding
- reports [Windows Forms], Windows Forms
- lookup tables [Windows Forms], data binding
- data [Windows Forms], complex data binding
- data binding [Windows Forms], Windows Forms
- data [Windows Forms], simple data binding
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: 419aac5e-819b-4aad-88b0-73a2f8c0bd27
ms.openlocfilehash: c5cb16d57dde35ca3b243191f27ea118cf19a680
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742325"
---
# <a name="data-binding-and-windows-forms"></a>Data binding e Windows Form
Nei Windows Form è possibile effettuare associazioni non solo alle origini dati tradizionali, ma anche a quasi ogni struttura che contiene dati. È possibile effettuare associazioni a una matrice di valori che verranno calcolati in fase di esecuzione, letti da un file o derivati dai valori di altri controlli.  
  
 Inoltre, è possibile associare all'origine dati qualsiasi proprietà di qualunque controllo. Nelil data binding tradizionale viene in genere associata all'origine dati la proprietà relativa alla visualizzazione, ad esempio la proprietà <xref:System.Windows.Forms.Control.Text%2A> di un controllo <xref:System.Windows.Forms.TextBox>. Con la .NET Framework è anche possibile impostare altre proprietà tramite binding. È possibile usare l'associazione per eseguire le attività seguenti:  
  
- Impostazione della grafica di un controllo immagine.  
  
- Impostazione del colore di sfondo di uno o più controlli.  
  
- Impostazione delle dimensioni dei controlli.  
  
 In pratica, il data binding rappresenta un sistema automatico per l'impostazione di qualsiasi proprietà accessibile in fase di esecuzione di qualsiasi controllo del form.  
  
## <a name="types-of-data-binding"></a>Tipi di data binding  
 Nei Windows Form è possibile usare due tipi di data binding, ovvero l'associazione semplice e l'associazione complessa. I due tipi presentano vantaggi diversi.  
  
|Tipo di data binding|Descrizione|  
|--------------------------|-----------------|  
|Data binding semplice|Capacità di un controllo di eseguire l'associazione a un singolo elemento di dati, ad esempio il valore di una colonna in una tabella di dataset. Questo tipo di associazione viene solitamente usata per controlli quali <xref:System.Windows.Forms.TextBox> o <xref:System.Windows.Forms.Label>, vale a dire controlli che in genere visualizzano un unico valore. In realtà è possibile associare qualsiasi proprietà di un controllo a un campo di un database. In Visual Studio è disponibile un supporto completo per questa funzionalità.<br /><br /> Per altre informazioni, vedere:<br /><br /> [interfacce di -   correlate all'associazione dati](interfaces-related-to-data-binding.md)<br />-   [procedura: esplorare i dati in Windows Forms](how-to-navigate-data-in-windows-forms.md)<br />-   [procedura: creare un controllo con associazione semplice in un Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)|  
|Data binding complesso|Capacità di un controllo di eseguire l'associazione a più di un elemento di dati, in genere a più record di un database. L'associazione complessa viene detta anche associazione basata su elenchi. Tra i controlli di esempio che supportano l'associazione complessa sono annoverati i controlli <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.ListBox> e <xref:System.Windows.Forms.ComboBox>. Per un esempio di data binding complesse, vedere [procedura: associare un controllo ComboBox o ListBox Windows Forms ai dati](./controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md).|  
  
## <a name="bindingsource-component"></a>Componente BindingSource  
 Per semplificare il data binding, Windows Form consente di associare un'origine dati al componente <xref:System.Windows.Forms.BindingSource> e poi di associare i controlli alla classe <xref:System.Windows.Forms.BindingSource>. È possibile usare la classe <xref:System.Windows.Forms.BindingSource> in scenari di associazione semplice o complessa. In entrambi i casi, la classe <xref:System.Windows.Forms.BindingSource> agisce da intermediaria tra l'origine dati e i controlli associati fornendo la notifica delle modifiche, la gestione della diffusione dei dati e altri servizi.  
  
## <a name="common-scenarios-that-employ-data-binding"></a>Scenari comuni di utilizzo del data binding  
 In quasi tutte le applicazioni commerciali vengono usate informazioni che sono lette da origini dati di un determinato tipo, generalmente tramite data binding. Nell'elenco seguente sono illustrati gli scenari più comuni in cui viene usato il data binding per la presentazione e la manipolazione dei dati.  
  
|Scenario|Descrizione|  
|--------------|-----------------|  
|Reporting|I report forniscono una soluzione flessibile per la visualizzazione e il riepilogo dei dati in un documento stampato. In genere vengono creati report che consentono di visualizzare un determinato contenuto di un'origine dati sia sullo schermo che su documenti stampati. I report più comuni includono elenchi, fatture e riepiloghi. Le voci dei report in genere vengono formattate in colonne di elenchi, con voci secondarie organizzate sotto ciascuna voce dell'elenco, tuttavia è opportuno scegliere il layout più appropriato in funzione del tipo di dati.|  
|Immissione di dati|Un metodo comunemente impiegato per immettere elevate quantità di dati correlati o per richiedere informazioni agli utenti consiste nell'utilizzo di un form per l'immissione dei dati. Gli utenti possono immettere le informazioni o selezionare le opzioni usando caselle di testo, pulsanti di opzione, elenchi a discesa e caselle di controllo. Le informazioni vengono quindi inviate e archiviate in un database, la cui struttura si basa sulle informazioni immesse.|  
|Relazione Master-Details|Un'applicazione Master-Details rappresenta un formato per la presentazione di dati correlati. Nello specifico, due tabelle di dati sono associate tra loro mediante una relazione. In un tipico scenario aziendale, ad esempio, sono disponibili una tabella "Customers" e una tabella "Orders" correlate da una relazione che collega i clienti ai relativi ordini. Per altre informazioni sulla creazione di un'applicazione Master-Details con due controlli <xref:System.Windows.Forms.DataGridView> Windows Forms, vedere [procedura: creare un form Master-Details con due controlli DataGridView Windows Forms](./controls/create-a-master-detail-form-using-two-datagridviews.md)|  
|Tabella di ricerca|Un altro scenario comune di presentazione e manipolazione dei dati è rappresentato dalla tabella di ricerca. Nell'ambito della visualizzazione di un'elevata quantità di dati viene spesso usato un controllo <xref:System.Windows.Forms.ComboBox> per visualizzare e manipolare i dati. I dati visualizzati nel controllo <xref:System.Windows.Forms.ComboBox> sono diversi dai dati scritti nel database. Se ad esempio è presente un controllo <xref:System.Windows.Forms.ComboBox> che visualizza i prodotti disponibili in un negozio di alimentari, probabilmente si vorranno visualizzare i nomi dei prodotti, quali pane, latte, uova e così via. Per facilitare tuttavia il recupero delle informazioni all'interno del database e per la normalizzazione del database, le informazioni per i prodotti specifici di un determinato ordine verranno probabilmente archiviate come numeri, ad esempio 501, 603 e così via. In tal modo viene stabilito un collegamento implicito tra il nome comune del prodotto nel controllo <xref:System.Windows.Forms.ComboBox> del form e il relativo numero presente all'interno dell'ordine. Ciò rappresenta in sintesi il principio di funzionamento di una tabella di ricerca. Per altre informazioni, vedere [procedura: creare una tabella di ricerca con il componente Windows Forms BindingSource](./controls/how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component.md).|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Binding>
- [Data binding in Windows Form](windows-forms-data-binding.md)
- [Procedura: Associare il controllo DataGrid Windows Form a un'origine dati](./controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Componente BindingSource](./controls/bindingsource-component.md)
