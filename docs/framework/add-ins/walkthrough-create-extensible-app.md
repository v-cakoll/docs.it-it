---
title: "Procedura dettagliata: creazione di un'applicazione estendibile"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292447fa3cf2dbad70dbfef32b7c184b250ed25e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-creating-an-extensible-application"></a>Procedura dettagliata: creazione di un'applicazione estendibile
Questa procedura dettagliata viene descritto come creare una pipeline per un componente aggiuntivo che esegue funzioni calcolatrice semplice. Viene illustrato uno scenario reale; invece, vengono illustrate le funzionalità di base di una pipeline e un componente aggiuntivo può come fornire servizi per un host.  
  
 Questa procedura dettagliata vengono descritte le attività seguenti:  
  
-   Creazione di una soluzione di Visual Studio.  
  
-   Creazione della struttura di directory della pipeline.  
  
-   Creazione del contratto e viste.  
  
-   Creazione dell'adattatore sul lato del componente aggiuntivo.  
  
-   Creazione dell'adattatore sul lato host.  
  
-   Creazione dell'host.  
  
-   Creazione del componente aggiuntivo.  
  
-   Distribuzione della pipeline.  
  
-   Esecuzione dell'applicazione host.  
  
 Questa pipeline passa solo tipi serializzabili (<xref:System.Double> e <xref:System.String>), tra l'host e il componente aggiuntivo. Per un esempio che illustra come passare raccolte di tipi di dati complessi, vedere [procedura dettagliata: passaggio di raccolte tra host e Add-Ins](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).  
  
 Il contratto per la pipeline definisce un modello a oggetti di quattro operazioni aritmetiche: aggiungere, sottrarre, moltiplicare e dividere. L'host fornisce il componente aggiuntivo con un'equazione per calcolare, ad esempio 2 + 2 e il componente aggiuntivo restituisce il risultato all'host.  
  
 Versione 2 del componente aggiuntivo calcolatrice fornisce maggiori possibilità di calcolo e viene illustrato il controllo delle versioni. Viene descritto in [procedura dettagliata: abilitare la compatibilità come le modifiche di Host](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, sono necessari i seguenti elementi:  
  
-   Visual Studio.  
  
## <a name="creating-a-visual-studio-solution"></a>Creazione di una soluzione di Visual Studio  
 Usare una soluzione in Visual Studio per contenere i progetti dei segmenti di pipeline.  
  
#### <a name="to-create-the-pipeline-solution"></a>Per creare la soluzione di pipeline  
  
1.  In Visual Studio, creare un nuovo progetto denominato `Calc1Contract`. Come base il **libreria di classi** modello.  
  
2.  Denominare la soluzione `CalculatorV1`.  
  
## <a name="creating-the-pipeline-directory-structure"></a>Creazione della struttura di Directory della Pipeline  
 Il modello di componente aggiuntivo richiede gli assembly dei segmenti della pipeline si trovino in una struttura di directory specificato. Per ulteriori informazioni sulla struttura della pipeline, vedere [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>Per creare la struttura di directory della pipeline  
  
1.  Creare una cartella dell'applicazione in un punto qualsiasi nel computer in uso.  
  
2.  In tale cartella, creare la struttura seguente:  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     Non è necessario inserire la struttura di cartelle della pipeline nella cartella dell'applicazione; viene eseguita qui solo per comodità. Nel passaggio appropriato, la procedura dettagliata viene illustrato come modificare il codice se la struttura di cartelle della pipeline si trova in un percorso diverso. Vedere la sezione requisiti della pipeline directory [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
    > [!NOTE]
    >  Il `CalcV2` cartella non viene usata in questa procedura dettagliata, è un segnaposto per [procedura dettagliata: abilitare la compatibilità come le modifiche di Host](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="creating-the-contract-and-views"></a>Creazione del contratto e viste  
 Definisce il segmento dei contratti per la pipeline di `ICalc1Contract` interfaccia che definisce i quattro metodi: `add`, `subtract`, `multiply`, e `divide`.  
  
#### <a name="to-create-the-contract"></a>Per creare il contratto  
  
1.  Nella soluzione di Visual Studio denominata `CalculatorV1`, aprire il `Calc1Contract` progetto.  
  
2.  In **Esplora**, aggiungere riferimenti agli assembly riportati di seguito per il `Calc1Contract` progetto:  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  In **Esplora**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti.  
  
4.  In **Esplora**, aggiungere un nuovo elemento al progetto, tramite il **interfaccia** modello. Nel **Aggiungi nuovo elemento** nella finestra di dialogo Nome l'interfaccia `ICalc1Contract`.  
  
5.  Nel file di interfaccia, aggiungere riferimenti a spazi dei nomi per <xref:System.AddIn.Contract> e <xref:System.AddIn.Pipeline>.  
  
6.  Utilizzare il codice seguente per completare questo segmento del contratto. Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInContractAttribute> attributo.  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  Facoltativamente, compilare la soluzione di Visual Studio. Impossibile eseguire la soluzione fino a quando la procedura finale, ma la compilazione al termine di ogni procedura garantisce che ogni progetto sia correggere.  
  
 Poiché la vista del componente aggiuntivo e la visualizzazione host del componente aggiuntivo è in genere presentano lo stesso codice, in particolare nella prima versione di un componente aggiuntivo, è possibile creare facilmente le viste nello stesso momento. Si differenziano per un solo fattore: la vista del componente aggiuntivo richiede il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo, mentre la visualizzazione host del componente aggiuntivo non richiede attributi.  
  
#### <a name="to-create-the-add-in-view"></a>Per creare la vista del componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `Calc1AddInView` per il `CalculatorV1` soluzione. Come base il **libreria di classi** modello.  
  
2.  In **Esplora**, aggiungere un riferimento a System.AddIn.dll per il `Calc1AddInView` progetto.  
  
3.  In **Esplora**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, tramite il **interfaccia** modello. Nel **Aggiungi nuovo elemento** nella finestra di dialogo Nome l'interfaccia `ICalculator`.  
  
4.  Nel file di interfaccia, aggiungere un riferimento dello spazio dei nomi <xref:System.AddIn.Pipeline>.  
  
5.  Utilizzare il codice seguente per completare questa vista del componente aggiuntivo. Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo.  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  Facoltativamente, compilare la soluzione di Visual Studio.  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>Per creare la visualizzazione host del componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `Calc1HVA` per il `CalculatorV1` soluzione. Come base il **libreria di classi** modello.  
  
2.  In **Esplora**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, tramite il **interfaccia** modello. Nel **Aggiungi nuovo elemento** nella finestra di dialogo Nome l'interfaccia `ICalculator`.  
  
3.  Nel file di interfaccia, utilizzare il codice seguente per completare la visualizzazione host del componente aggiuntivo.  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-add-in-side-adapter"></a>Creazione dell'adattatore sul lato componente-  
 Questo adattatore sul lato componente-è costituito da una scheda visualizzazione-contratto. Questo segmento di pipeline converte i tipi della vista del componente aggiuntivo per il contratto.  
  
 In questa pipeline, il componente aggiuntivo fornisce un servizio all'host e i tipi di flusso dal componente aggiuntivo per l'host. Poiché non vengono passati tipi dall'host per il componente aggiuntivo, non è necessario includere un adattatore contratto-visualizzazione sul lato componente della pipeline.  
  
#### <a name="to-create-the-add-in-side-adapter"></a>Per creare l'adattatore lato del componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `Calc1AddInSideAdapter` per il `CalculatorV1` soluzione. Come base il **libreria di classi** modello.  
  
2.  In **Esplora**, aggiungere riferimenti agli assembly riportati di seguito per il `Calc1AddInSideAdapter` progetto:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Aggiungere riferimenti ai progetti per i segmenti della pipeline adiacenti:  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  Selezionare ogni riferimento a progetto e in **proprietà** impostare **Copia localmente** a **False**. In Visual Basic, usare il **riferimenti** scheda della **le proprietà del progetto** impostare **Copia localmente** per **False** per i due riferimenti al progetto.  
  
5.  Rinominare la classe del progetto predefinita `CalculatorViewToContractAddInSideAdapter`.  
  
6.  Nel file di classe, aggiungere riferimenti a spazi dei nomi per <xref:System.AddIn.Pipeline>.  
  
7.  Nel file di classe, aggiungere riferimenti a spazi dei nomi per i segmenti adiacenti: `CalcAddInViews` e `CalculatorContracts`. (In Visual Basic, questi riferimenti dello spazio dei nomi sono `Calc1AddInView.CalcAddInViews` e `Calc1Contract.CalculatorContracts`, a meno che non è stato disattivato gli spazi dei nomi predefinito nei progetti di Visual Basic.)  
  
8.  Applicare il <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attributo il `CalculatorViewToContractAddInSideAdapter` (classe), per identificarla come adattatore sul lato del componente aggiuntivo.  
  
9. Rendere il `CalculatorViewToContractAddInSideAdapter` classe ereditare <xref:System.AddIn.Pipeline.ContractBase>, che fornisce un'implementazione predefinita del <xref:System.AddIn.Contract.IContract> di interfaccia e implementare l'interfaccia del contratto per la pipeline, `ICalc1Contract`.  
  
10. Aggiungere un costruttore pubblico che accetta un `ICalculator`, memorizza nella cache in un campo privato e chiama il costruttore di classe di base.  
  
11. Per implementare i membri di `ICalc1Contract`, è sufficiente chiamare i membri corrispondenti del `ICalculator` istanza che viene passato al costruttore e restituisce i risultati. In questo modo la visualizzazione (`ICalculator`) al contratto (`ICalc1Contract`).  
  
     Il codice seguente illustra l'adattatore sul lato componente-completato.  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-host-side-adapter"></a>Creazione dell'adattatore sul lato Host  
 Questo adattatore sul lato host è costituito da una scheda di contratto per visualizzare. Questo segmento adatta il contratto per la visualizzazione host del componente aggiuntivo.  
  
 Nella pipeline, il componente aggiuntivo fornisce un servizio per l'host e il flusso di tipi di componente aggiuntivo per l'host. Poiché non vengono passati tipi dall'host per il componente aggiuntivo, non è necessario includere un adattatore visualizzazione-contratto.  
  
 Per implementare la gestione della durata, utilizzare un <xref:System.AddIn.Pipeline.ContractHandle> oggetto per associare un token di durata per il contratto. È necessario mantenere un riferimento a questo punto di controllo affinché le operazioni di gestione della durata. Dopo il token viene applicato, alcuna programmazione aggiuntiva non è necessaria perché il sistema del componente aggiuntivo è possibile eliminare gli oggetti quando non è più in uso e renderli disponibili per l'operazione di garbage collection. Per ulteriori informazioni, vedere [la gestione della durata](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
#### <a name="to-create-the-host-side-adapter"></a>Per creare l'adattatore sul lato host  
  
1.  Aggiungere un nuovo progetto denominato `Calc1HostSideAdapter` per il `CalculatorV1` soluzione. Come base il **libreria di classi** modello.  
  
2.  In **Esplora**, aggiungere riferimenti agli assembly riportati di seguito per il `Calc1HostSideAdapter` progetto:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Aggiungere riferimenti ai progetti per i segmenti adiacenti:  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  Selezionare ogni riferimento a progetto e in **proprietà** impostare **Copia localmente** a **False**. In Visual Basic, usare il **riferimenti** scheda della **le proprietà del progetto** impostare **Copia localmente** per **False** per i due riferimenti al progetto.  
  
5.  Rinominare la classe del progetto predefinita `CalculatorContractToViewHostSideAdapter`.  
  
6.  Nel file di classe, aggiungere riferimenti a spazi dei nomi per <xref:System.AddIn.Pipeline>.  
  
7.  Nel file di classe, aggiungere riferimenti a spazi dei nomi per i segmenti adiacenti: `CalcHVAs` e `CalculatorContracts`. (In Visual Basic, questi riferimenti dello spazio dei nomi sono `Calc1HVA.CalcHVAs` e `Calc1Contract.CalculatorContracts`, a meno che non è stato disattivato gli spazi dei nomi predefinito nei progetti di Visual Basic.)  
  
8.  Applicare il <xref:System.AddIn.Pipeline.HostAdapterAttribute> attributo il `CalculatorContractToViewHostSideAdapter` (classe), per facilitarne l'identificazione del segmento di adattatore sul lato host.  
  
9. Rendere il `CalculatorContractToViewHostSideAdapter` classe implementa l'interfaccia che rappresenta la visualizzazione host del componente aggiuntivo: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).  
  
10. Aggiungere un costruttore pubblico che accetta il tipo di contratto della pipeline, `ICalc1Contract`. Il costruttore deve memorizzare nella cache il riferimento al contratto. Inoltre necessario creare e memorizzare nella cache un nuovo <xref:System.AddIn.Pipeline.ContractHandle> per il contratto, per gestire la durata del componente aggiuntivo.  
  
    > [!IMPORTANT]
    >  Il <xref:System.AddIn.Pipeline.ContractHandle> è fondamentale per la gestione della durata. Se non si riesce a mantenere un riferimento per il <xref:System.AddIn.Pipeline.ContractHandle> dell'oggetto, quest ' ultimo verrà recuperato dalla procedura di garbage collection e la pipeline verrà interrotta quando il programma non previsto. Questo può causare errori difficili da diagnosticare, ad esempio <xref:System.AppDomainUnloadedException>. L'arresto è una fase normale il ciclo di vita di una pipeline, in modo non è possibile per il codice di gestione del ciclo di vita rilevare che questa condizione è un errore.  
  
11. Per implementare i membri di `ICalculator`, è sufficiente chiamare i membri corrispondenti del `ICalc1Contract` istanza che viene passato al costruttore e restituisce i risultati. In questo modo il contratto (`ICalc1Contract`) per la visualizzazione (`ICalculator`).  
  
     Il codice seguente illustra l'adattatore sul lato host completato.  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-host"></a>La creazione dell'Host  
 Un'applicazione host interagisce con il componente aggiuntivo tramite la visualizzazione host del componente aggiuntivo. Utilizza i metodi di individuazione e attivazione del componente aggiuntivo forniti dal <xref:System.AddIn.Hosting.AddInStore> e <xref:System.AddIn.Hosting.AddInToken> classi per eseguire le operazioni seguenti:  
  
-   Aggiornare la cache di informazioni sulla pipeline e componente aggiuntivo.  
  
-   Trovare i componenti aggiuntivi del tipo di visualizzazione host, `ICalculator`, nella directory radice della pipeline specificata.  
  
-   Richiedere all'utente di specificare il componente aggiuntivo da utilizzare.  
  
-   Attivare il componente aggiuntivo selezionato in un nuovo dominio applicazione con un livello di attendibilità di sicurezza specificato.  
  
-   Eseguire personalizzata `RunCalculator` metodo, che chiama i metodi del componente aggiuntivo come specificato dalla visualizzazione host del componente aggiuntivo.  
  
#### <a name="to-create-the-host"></a>Per creare l'host  
  
1.  Aggiungere un nuovo progetto denominato `Calc1Host` per il `CalculatorV1` soluzione. Come base il **applicazione Console** modello.  
  
2.  In **Esplora**, aggiungere un riferimento all'assembly System.AddIn.dll per il `Calc1Host` progetto.  
  
3.  Aggiungere un riferimento al progetto il `Calc1HVA` progetto. Selezionare il riferimento al progetto e in **proprietà** impostare **Copia localmente** a **False**. In Visual Basic, usare il **riferimenti** scheda **le proprietà del progetto** per impostare **Copia localmente** per **False**.  
  
4.  Rinominare il file di classe (modulo di Visual Basic) `MathHost1`.  
  
5.  In Visual Basic, usare il **applicazione** scheda della finestra di **le proprietà del progetto** la finestra di dialogo per impostare **oggetto di avvio** per **Sub Main**.  
  
6.  Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn.Hosting>.  
  
7.  Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi per la visualizzazione host del componente aggiuntivo: `CalcHVAs`. (In Visual Basic, questo spazio dei nomi riferimento è `Calc1HVA.CalcHVAs`, a meno che non è stato disattivato gli spazi dei nomi predefinito nei progetti di Visual Basic.)  
  
8.  In **Esplora**, selezionare la soluzione e dal **progetto** dal menu **proprietà**. Nel **pagine proprietà soluzione** la finestra di dialogo, impostare il **progetto di avvio singolo** da questo progetto di applicazione host.  
  
9. Nel file di classe o modulo, usare il <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> metodo per aggiornare la cache. Utilizzare il <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> metodo per ottenere una raccolta di token, utilizzare il <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> metodo per attivare un componente aggiuntivo.  
  
     Il codice seguente illustra l'applicazione host completata.  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  Questo codice si presuppone che la struttura di cartelle della pipeline si trova nella cartella dell'applicazione. Se si trova in un' posizione, modificare la riga di codice che imposta il `addInRoot` variabile, in modo che la variabile contiene il percorso per la struttura di directory della pipeline.  
  
     Il codice Usa un `ChooseCalculator` metodo per elencare i token e richiedere all'utente di scegliere un componente aggiuntivo. Il `RunCalculator` metodo richiede l'immissione di espressioni semplici operazioni matematiche, analizza le espressioni utilizzando la `Parser` classe e consente di visualizzare i risultati restituiti dal componente aggiuntivo.  
  
10. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-add-in"></a>Creare il componente aggiuntivo  
 Un componente aggiuntivo implementa i metodi specificati da parte della vista del componente aggiuntivo. Questo componente aggiuntivo implementa il `Add`, `Subtract`, `Multiply`, e `Divide` operazioni e restituisce i risultati all'host.  
  
#### <a name="to-create-the-add-in"></a>Per creare il componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `AddInCalcV1` per il `CalculatorV1` soluzione. Come base il **libreria di classi** modello.  
  
2.  In **Esplora**, aggiungere un riferimento all'assembly System.AddIn.dll al progetto.  
  
3.  Aggiungere un riferimento al progetto il `Calc1AddInView` progetto. Selezionare il riferimento al progetto e in **proprietà**, impostare **Copia localmente** a **False**. In Visual Basic, usare il **riferimenti** scheda **le proprietà del progetto** per impostare **Copia localmente** per **False** per il riferimento al progetto.  
  
4.  Rinominare la classe `AddInCalcV1`.  
  
5.  Nel file di classe, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn> e il segmento di visualizzazione: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).  
  
6.  Applicare il <xref:System.AddIn.AddInAttribute> attributo il `AddInCalcV1` (classe), per identificare la classe come un componente aggiuntivo.  
  
7.  Rendere il `AddInCalcV1` classe implementa l'interfaccia che rappresenta la vista del componente aggiuntivo: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).  
  
8.  Implementare i membri di `ICalculator` restituendo i risultati dei calcoli appropriati.  
  
     Il codice seguente viene illustrato il componente aggiuntivo completato.  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="deploying-the-pipeline"></a>Distribuzione della Pipeline  
 A questo punto si è pronti compilare e distribuire i segmenti del componente aggiuntivo per la struttura di directory della pipeline richiesta.  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>Per distribuire i segmenti della pipeline  
  
1.  Per ogni progetto nella soluzione, utilizzare il **compilare** scheda della **le proprietà del progetto** (il **compilare** scheda in Visual Basic) per impostare il valore della **percorso di Output**  (il **il percorso di output di compilazione** in Visual Basic). Se la cartella dell'applicazione denominata `MyApp`, ad esempio, i progetti saranno compilati nelle cartelle seguenti:  
  
    |Progetto|Path|  
    |-------------|----------|  
    |AddInCalcV1|MyApp\Pipeline\AddIns\CalcV1|  
    |Calc1AddInSideAdapter|MyApp\Pipeline\AddInSideAdapters|  
    |Calc1AddInView|MyApp\Pipeline\AddInViews|  
    |Calc1Contract|MyApp\Pipeline\Contracts|  
    |Calc1Host|MyApp|  
    |Calc1HostSideAdapter|MyApp\Pipeline\HostSideAdapters|  
    |Calc1HVA|MyApp|  
  
    > [!NOTE]
    >  Se si è deciso di inserire la struttura di cartelle della pipeline in un percorso diverso dalla cartella dell'applicazione, è necessario modificare di conseguenza i percorsi mostrati nella tabella. Vedere la sezione requisiti della pipeline directory [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
2.  Compilare la soluzione di Visual Studio.  
  
3.  Controllare le directory della pipeline e di applicazione per assicurarsi che gli assembly sono stati copiati nelle directory corrette e che nessun copie aggiuntive di assembly siano state installate nelle cartelle errate.  
  
    > [!NOTE]
    >  Se non è stato modificato **Copia localmente** a **False** per il `Calc1AddInView` riferimento nel progetto di `AddInCalcV1` progetto, problemi relativi al contesto del caricatore impedirà il componente aggiuntivo si trovano.  
  
     Per informazioni su come distribuire la pipeline, vedere [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
## <a name="running-the-host-application"></a>Esecuzione dell'applicazione Host  
 A questo punto si è pronti eseguire l'host e interagire con il componente aggiuntivo.  
  
#### <a name="to-run-the-host-application"></a>Per eseguire l'applicazione host  
  
1.  Al prompt dei comandi, passare alla directory dell'applicazione ed eseguire l'applicazione host, `Calc1Host.exe`.  
  
2.  L'host consente di individuare tutti i componenti aggiuntivi disponibili del tipo e viene richiesto di selezionare un componente aggiuntivo. Immettere **1** per il componente aggiuntivo è disponibile solo.  
  
3.  Immettere un'equazione per il calcolo, ad esempio **2 + 2**. Devono essere presenti spazi tra i numeri e l'operatore.  
  
4.  Tipo **uscire** e premere il **invio** tasto per chiudere l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Abilitazione della compatibilità con le versioni precedenti in base alle modifiche dell'Host](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [Procedura dettagliata: Passaggio di raccolte tra componenti aggiuntivi e host](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [Requisiti di sviluppo pipeline](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [Contratti, viste e le schede](http://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [Sviluppo pipeline](../../../docs/framework/add-ins/pipeline-development.md)
