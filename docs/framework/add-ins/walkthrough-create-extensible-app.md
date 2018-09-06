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
ms.openlocfilehash: 5d2aaeaffaf3abbe1e8efcdb57d40e6ae60f89b5
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875096"
---
# <a name="walkthrough-creating-an-extensible-application"></a>Procedura dettagliata: creazione di un'applicazione estendibile
Questa procedura dettagliata descrive come creare una pipeline per un componente aggiuntivo che esegue funzioni semplice calcolatrice. Se non illustra uno scenario reale; piuttosto, illustra le funzionalità di base di una pipeline e un componente aggiuntivo può come forniscono servizi per un host.  
  
 Questa procedura dettagliata descrive le attività seguenti:  
  
-   Creazione di una soluzione di Visual Studio.  
  
-   Creazione della struttura di directory della pipeline.  
  
-   Creazione del contratto e le viste.  
  
-   Creazione dell'adattatore lato componente aggiuntivo.  
  
-   Creazione dell'adattatore lato host.  
  
-   Creazione dell'host.  
  
-   Creare il componente aggiuntivo.  
  
-   Distribuzione della pipeline.  
  
-   Esecuzione dell'applicazione host.  
  
 Questa pipeline passa solo tipi serializzabili (<xref:System.Double> e <xref:System.String>), tra l'host e il componente aggiuntivo. Per un esempio che illustra come passare raccolte di tipi di dati complessi, vedere [procedura dettagliata: passaggio di raccolte tra host e Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).  
  
 Il contratto per questa pipeline consente di definire un modello a oggetti delle quattro operazioni aritmetiche: aggiunta, sottrazione, moltiplicazione e divisione. L'host fornisce il componente aggiuntivo con un'equazione per calcolare, ad esempio 2 + 2, e il componente aggiuntivo restituisce il risultato all'host.  
  
 Versione 2 del componente aggiuntivo per la calcolatrice offre maggiori possibilità di calcolo e viene illustrato il controllo delle versioni. Viene descritto in [procedura dettagliata: abilitazione della compatibilità con le versioni precedenti come le modifiche di Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, sono necessari i seguenti elementi:  
  
-   Visual Studio.  
  
## <a name="creating-a-visual-studio-solution"></a>Creazione di una soluzione di Visual Studio  
 Usare una soluzione in Visual Studio per contenere i progetti dei segmenti di pipeline.  
  
#### <a name="to-create-the-pipeline-solution"></a>Per creare la soluzione della pipeline  
  
1.  In Visual Studio, creare un nuovo progetto denominato `Calc1Contract`. Basandosi sul **libreria di classi** modello.  
  
2.  Denominare la soluzione `CalculatorV1`.  
  
## <a name="creating-the-pipeline-directory-structure"></a>Creazione della struttura di Directory della Pipeline  
 Il modello di componente aggiuntivo richiede gli assembly di segmenti della pipeline a essere inserito in una struttura di directory specificato. Per altre informazioni sulla struttura della pipeline, vedere [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>Per creare la struttura di directory della pipeline  
  
1.  Creare una cartella dell'applicazione in un punto qualsiasi nel computer.  
  
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
  
     Non è necessario inserire la struttura di cartelle della pipeline nella cartella dell'applicazione; viene eseguita qui solo per comodità. Nel passaggio appropriato, la procedura dettagliata illustra come modificare il codice, se la struttura di cartelle della pipeline si trova in una posizione diversa. Vedere la discussione dei requisiti di directory della pipeline [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
    > [!NOTE]
    >  Il `CalcV2` cartella non viene usata in questa procedura dettagliata; è un segnaposto per [questa procedura dettagliata: abilitazione della compatibilità con le versioni precedenti come le modifiche di Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="creating-the-contract-and-views"></a>Creazione del contratto e le viste  
 Il segmento di contratto per la pipeline definisce i `ICalc1Contract` interfaccia che definisce quattro metodi: `add`, `subtract`, `multiply`, e `divide`.  
  
#### <a name="to-create-the-contract"></a>Per creare il contratto  
  
1.  Nella soluzione di Visual Studio denominata `CalculatorV1`, aprire il `Calc1Contract` progetto.  
  
2.  Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly seguenti per il `Calc1Contract` progetto:  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  Nelle **Esplora soluzioni**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti.  
  
4.  Nelle **Esplora soluzioni**, aggiungere un nuovo elemento al progetto, utilizzando il **interfaccia** modello. Nel **Aggiungi nuovo elemento** della finestra di dialogo Nome interfaccia `ICalc1Contract`.  
  
5.  Nel file di interfaccia, aggiungere i riferimenti di spazio dei nomi per <xref:System.AddIn.Contract> e <xref:System.AddIn.Pipeline>.  
  
6.  Usare il codice seguente per completare questo segmento di contratto. Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInContractAttribute> attributo.  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  Facoltativamente, compilare la soluzione di Visual Studio. La soluzione non può essere eseguita fino a quando la procedura finale, ma la compilazione al termine di ogni procedura garantisce che ogni progetto è correggere.  
  
 Poiché la visualizzazione componente aggiuntivo e la visualizzazione host del componente aggiuntivo hanno in genere lo stesso codice, in particolare nella prima versione di un componente aggiuntivo, è possibile creare facilmente le viste nello stesso momento. Si differenziano per un solo fattore: richiede la visualizzazione componente aggiuntivo di <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo, mentre la visualizzazione host del componente aggiuntivo non richiede tutti gli attributi.  
  
#### <a name="to-create-the-add-in-view"></a>Per creare la visualizzazione componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `Calc1AddInView` per il `CalculatorV1` soluzione. Basandosi sul **libreria di classi** modello.  
  
2.  Nelle **Esplora soluzioni**, aggiungere un riferimento a System.AddIn.dll per il `Calc1AddInView` progetto.  
  
3.  Nelle **Esplora soluzioni**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, utilizzando il **interfaccia** modello. Nel **Aggiungi nuovo elemento** della finestra di dialogo Nome interfaccia `ICalculator`.  
  
4.  Nel file di interfaccia, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn.Pipeline>.  
  
5.  Usare il codice seguente per completare questa visualizzazione componente aggiuntivo. Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo.  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  Facoltativamente, compilare la soluzione di Visual Studio.  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>Per creare la visualizzazione host del componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `Calc1HVA` per il `CalculatorV1` soluzione. Basandosi sul **libreria di classi** modello.  
  
2.  Nelle **Esplora soluzioni**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, utilizzando il **interfaccia** modello. Nel **Aggiungi nuovo elemento** della finestra di dialogo Nome interfaccia `ICalculator`.  
  
3.  Nel file di interfaccia, usare il codice seguente per completare la visualizzazione host del componente aggiuntivo.  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-add-in-side-adapter"></a>Creazione dell'adattatore sul lato del componente:  
 Questo adapter in-sul lato del componente è costituito da un adattatore visualizzazione-contratto. Questo segmento di pipeline converte i tipi dalla visualizzazione componente aggiuntivo per il contratto.  
  
 In questa pipeline, il componente aggiuntivo fornisce un servizio all'host e i tipi di flusso dal componente aggiuntivo all'host. Poiché nessun tipo di flusso dall'host al componente aggiuntivo, non è necessario includere un adattatore contratto-visualizzazione sul lato componente aggiuntivo della pipeline.  
  
#### <a name="to-create-the-add-in-side-adapter"></a>Per creare l'adattatore lato componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `Calc1AddInSideAdapter` per il `CalculatorV1` soluzione. Basandosi sul **libreria di classi** modello.  
  
2.  Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly seguenti per il `Calc1AddInSideAdapter` progetto:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Aggiungere riferimenti al progetto per i progetti per i segmenti di pipeline adiacente:  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  Selezionare ogni riferimento al progetto e nella **delle proprietà** impostare **Copia localmente** al **False**. In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False** per i due riferimenti al progetto.  
  
5.  Rinominare la classe del progetto predefinita `CalculatorViewToContractAddInSideAdapter`.  
  
6.  Nel file di classe, aggiungere i riferimenti di spazio dei nomi a <xref:System.AddIn.Pipeline>.  
  
7.  Nel file di classe, aggiungere i riferimenti di spazio dei nomi per i segmenti adiacenti: `CalcAddInViews` e `CalculatorContracts`. (In Visual Basic, sono questi riferimenti dello spazio dei nomi `Calc1AddInView.CalcAddInViews` e `Calc1Contract.CalculatorContracts`, a meno che non siano stati disattivati gli spazi dei nomi predefinito nei progetti Visual Basic.)  
  
8.  Si applicano i <xref:System.AddIn.Pipeline.AddInAdapterAttribute> dell'attributo di `CalculatorViewToContractAddInSideAdapter` (classe), venga identificato come l'adattatore lato componente aggiuntivo.  
  
9. Rendere la `CalculatorViewToContractAddInSideAdapter` classe ereditare <xref:System.AddIn.Pipeline.ContractBase>, che fornisce un'implementazione predefinita delle <xref:System.AddIn.Contract.IContract> interfaccia e implementare l'interfaccia del contratto per la pipeline `ICalc1Contract`.  
  
10. Aggiungere un costruttore pubblico che accetta un `ICalculator`, memorizza nella cache in un campo privato e chiama il costruttore di classe di base.  
  
11. Per implementare i membri del `ICalc1Contract`, è sufficiente chiamare i membri corrispondenti del `ICalculator` istanza che viene passato al costruttore e restituirà i risultati. In questo modo la visualizzazione (`ICalculator`) al contratto (`ICalc1Contract`).  
  
     Il codice seguente illustra l'adattatore sul lato del componente-completato.  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-host-side-adapter"></a>Creazione dell'adattatore sul lato Host  
 Questo adattatore lato host è costituito da un adattatore contratto-vista. Il segmento si adatta al contratto per la visualizzazione host del componente aggiuntivo.  
  
 In questa pipeline, il componente aggiuntivo fornisce un servizio per l'host e il flusso di tipi dal componente aggiuntivo all'host. Poiché nessun tipo di flusso dall'host al componente aggiuntivo, non è necessario includere un adattatore visualizzazione-contratto.  
  
 Per implementare la gestione della durata, usare un <xref:System.AddIn.Pipeline.ContractHandle> oggetto da associare un token di durata per il contratto. È necessario mantenere un riferimento a questo handle in ordine per la gestione della durata a funzionare. Dopo il token viene applicato, alcuna programmazione aggiuntiva non è necessaria perché il sistema del componente aggiuntivo possa eliminare gli oggetti quando non sono più in uso e renderli disponibili per l'operazione di garbage collection. Per altre informazioni, vedere [la gestione della durata](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
#### <a name="to-create-the-host-side-adapter"></a>Per creare l'adattatore lato host  
  
1.  Aggiungere un nuovo progetto denominato `Calc1HostSideAdapter` per il `CalculatorV1` soluzione. Basandosi sul **libreria di classi** modello.  
  
2.  Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly seguenti per il `Calc1HostSideAdapter` progetto:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Aggiungere riferimenti al progetto per i progetti per i segmenti adiacenti:  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  Selezionare ogni riferimento al progetto e nella **delle proprietà** impostare **Copia localmente** al **False**. In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False** per i due riferimenti al progetto.  
  
5.  Rinominare la classe del progetto predefinita `CalculatorContractToViewHostSideAdapter`.  
  
6.  Nel file di classe, aggiungere i riferimenti di spazio dei nomi a <xref:System.AddIn.Pipeline>.  
  
7.  Nel file di classe, aggiungere i riferimenti di spazio dei nomi per i segmenti adiacenti: `CalcHVAs` e `CalculatorContracts`. (In Visual Basic, sono questi riferimenti dello spazio dei nomi `Calc1HVA.CalcHVAs` e `Calc1Contract.CalculatorContracts`, a meno che non siano stati disattivati gli spazi dei nomi predefinito nei progetti Visual Basic.)  
  
8.  Si applicano i <xref:System.AddIn.Pipeline.HostAdapterAttribute> dell'attributo di `CalculatorContractToViewHostSideAdapter` (classe), per facilitarne l'identificazione del segmento di adattatore lato host.  
  
9. Verificare i `CalculatorContractToViewHostSideAdapter` classe implementare l'interfaccia che rappresenta la visualizzazione host del componente aggiuntivo: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).  
  
10. Aggiungere un costruttore pubblico che accetta il tipo di contratto di pipeline, `ICalc1Contract`. Il costruttore deve memorizzare nella cache il riferimento al contratto. Anche necessario creare e memorizzare nella cache un nuovo <xref:System.AddIn.Pipeline.ContractHandle> per il contratto, per gestire la durata del componente aggiuntivo.  
  
    > [!IMPORTANT]
    >  Il <xref:System.AddIn.Pipeline.ContractHandle> è fondamentale per la gestione della durata. Se non si riesce a mantenere un riferimento al <xref:System.AddIn.Pipeline.ContractHandle> dell'oggetto, quest ' ultimo verrà recuperato dalla procedura di garbage collection, e la pipeline si arresterà quando il programma non previsto. Questo può causare errori difficili da diagnosticare, ad esempio <xref:System.AppDomainUnloadedException>. Istruzione SHUTDOWN è una fase normale in tutta la durata di una pipeline, in modo che non è possibile per il codice di gestione di durata rilevare che questa condizione è un errore.  
  
11. Per implementare i membri del `ICalculator`, è sufficiente chiamare i membri corrispondenti del `ICalc1Contract` istanza che viene passato al costruttore e restituirà i risultati. In questo modo il contratto (`ICalc1Contract`) per la visualizzazione (`ICalculator`).  
  
     Il codice seguente illustra l'adattatore lato host completato.  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-host"></a>Creazione dell'Host  
 Un'applicazione host interagisce con il componente aggiuntivo tramite la visualizzazione host del componente aggiuntivo. Utilizza i metodi di individuazione e attivazione del componente aggiuntivo forniti dal <xref:System.AddIn.Hosting.AddInStore> e <xref:System.AddIn.Hosting.AddInToken> classi per eseguire le operazioni seguenti:  
  
-   Aggiornare la cache di informazioni sulla pipeline e componenti aggiuntivi.  
  
-   Trovare i componenti aggiuntivi del tipo di visualizzazione host, `ICalculator`, nella directory radice della pipeline specificata.  
  
-   Richiedere all'utente di specificare quale componente aggiuntivo da usare.  
  
-   Attivare il componente aggiuntivo selezionato in un nuovo dominio applicazione con un livello di attendibilità di sicurezza specificato.  
  
-   Eseguire l'oggetto personalizzato `RunCalculator` metodo, che chiama i metodi del componente aggiuntivo come specificato dalla visualizzazione host del componente aggiuntivo.  
  
#### <a name="to-create-the-host"></a>Per creare l'host  
  
1.  Aggiungere un nuovo progetto denominato `Calc1Host` per il `CalculatorV1` soluzione. Basandosi sul **applicazione Console** modello.  
  
2.  Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly System.AddIn.dll al `Calc1Host` progetto.  
  
3.  Aggiungere un riferimento al progetto il `Calc1HVA` progetto. Selezionare il riferimento al progetto e nella **delle proprietà** impostare **Copia localmente** al **False**. In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False**.  
  
4.  Rinominare il file di classe (modulo di Visual Basic) `MathHost1`.  
  
5.  In Visual Basic, usare il **applicazione** scheda della finestra di **le proprietà del progetto** la finestra di dialogo per impostare **oggetto di avvio** per **Sub Main**.  
  
6.  Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn.Hosting>.  
  
7.  Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi per la visualizzazione host del componente aggiuntivo: `CalcHVAs`. (In Visual Basic, il riferimento dello spazio dei nomi è `Calc1HVA.CalcHVAs`, a meno che non siano stati disattivati gli spazi dei nomi predefinito nei progetti Visual Basic.)  
  
8.  In **Esplora soluzioni**, selezionare la soluzione e dal **Project** dal menu **proprietà**. Nel **pagine proprietà soluzione** finestra di dialogo, impostare il **progetto di avvio singolo** da questo progetto di applicazione host.  
  
9. Nel file di classe o modulo, usare il <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> metodo per aggiornare la cache. Usare la <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> metodo per ottenere una raccolta di token e usare il <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> metodo per attivare un componente aggiuntivo.  
  
     Il codice seguente illustra l'applicazione host completata.  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  Questo codice presuppone che la struttura di cartelle della pipeline si trova nella cartella dell'applicazione. Se si trova in un' posizione, modificare la riga di codice che imposta il `addInRoot` variabile, in modo che la variabile contiene il percorso per la struttura di directory della pipeline.  
  
     Il codice Usa un `ChooseCalculator` metodo per elencare i token e per richiedere all'utente di scegliere un componente aggiuntivo. Il `RunCalculator` metodo richiede l'immissione di espressioni matematiche semplici, analizza le espressioni che usano il `Parser` classe e visualizza i risultati restituiti dal componente aggiuntivo.  
  
10. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="creating-the-add-in"></a>Creazione del componente aggiuntivo  
 Un componente aggiuntivo implementa i metodi specificati dalla visualizzazione componente aggiuntivo. Questo componente aggiuntivo implementa il `Add`, `Subtract`, `Multiply`, e `Divide` operazioni e restituisce i risultati per l'host.  
  
#### <a name="to-create-the-add-in"></a>Per creare il componente aggiuntivo  
  
1.  Aggiungere un nuovo progetto denominato `AddInCalcV1` per il `CalculatorV1` soluzione. Basandosi sul **libreria di classi** modello.  
  
2.  Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly System.AddIn.dll al progetto.  
  
3.  Aggiungere un riferimento al progetto il `Calc1AddInView` progetto. Selezionare il riferimento al progetto e nella **delle proprietà**, impostare **Copia localmente** al **False**. In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False** per il riferimento al progetto.  
  
4.  Rinominare la classe `AddInCalcV1`.  
  
5.  Nel file di classe, aggiungere un riferimento dello spazio dei nomi <xref:System.AddIn> e il segmento di visualizzazione componente aggiuntivo: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).  
  
6.  Si applicano i <xref:System.AddIn.AddInAttribute> dell'attributo di `AddInCalcV1` (classe), per identificare la classe come un componente aggiuntivo.  
  
7.  Verificare i `AddInCalcV1` classe implementare l'interfaccia che rappresenta la visualizzazione componente aggiuntivo: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).  
  
8.  Implementare i membri di `ICalculator` restituendo i risultati dei calcoli appropriati.  
  
     Il codice seguente illustra il componente aggiuntivo completato.  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. Facoltativamente, compilare la soluzione di Visual Studio.  
  
## <a name="deploying-the-pipeline"></a>Distribuzione della Pipeline  
 A questo punto si è pronti compilare e distribuire i segmenti del componente aggiuntivo per la struttura di directory della pipeline richiesta.  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>Per distribuire i segmenti della pipeline  
  
1.  Per ogni progetto nella soluzione, usare il **compilare** scheda della finestra **le proprietà del progetto** (la **compilare** scheda in Visual Basic) per impostare il valore del **percorso di Output**  (la **percorso di output di compilazione** in Visual Basic). Se la cartella dell'applicazione denominata `MyApp`, ad esempio, i progetti saranno compilati nelle cartelle seguenti:  
  
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
    >  Se si è deciso di mettere la struttura di cartelle di pipeline in un percorso diverso dalla cartella dell'applicazione, è necessario modificare i percorsi visualizzati nella tabella di conseguenza. Vedere la discussione dei requisiti di directory della pipeline [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
2.  Compilare la soluzione di Visual Studio.  
  
3.  Controllare le directory dell'applicazione e la pipeline per garantire che gli assembly sono stati copiati nelle directory corrette e che nessun copie aggiuntive di assembly siano state installate nelle cartelle non corrette.  
  
    > [!NOTE]
    >  Se non è stato modificato **Copia localmente** al **False** per il `Calc1AddInView` riferimento nel progetto di `AddInCalcV1` progetti, problemi di contesto del caricatore impedirà il componente aggiuntivo che si trova.  
  
     Per informazioni sulla distribuzione per la pipeline, vedere [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
## <a name="running-the-host-application"></a>Esecuzione dell'applicazione Host  
 A questo punto si è pronti eseguire l'host e interagire con il componente aggiuntivo.  
  
#### <a name="to-run-the-host-application"></a>Per eseguire l'applicazione host  
  
1.  Al prompt dei comandi, passare alla directory dell'applicazione ed eseguire l'applicazione host, `Calc1Host.exe`.  
  
2.  L'host consente di trovare tutti i componenti aggiuntivi disponibili del tipo e viene richiesto di selezionare un componente aggiuntivo. Immettere **1** per il componente aggiuntivo è disponibile solo.  
  
3.  Immettere un'equazione per la Calcolatrice, ad esempio **2 + 2**. Devono essere presenti spazi tra i numeri e l'operatore.  
  
4.  Tipo di **uscire** e premere il **invio** un tasto per chiudere l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Abilitazione della compatibilità con le versioni precedenti in base alle modifiche dell'Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [Procedura dettagliata: Passaggio di raccolte tra host e componenti aggiuntivi](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [Requisiti di sviluppo delle pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [Contratti, viste e adattatori](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [Sviluppo pipeline](../../../docs/framework/add-ins/pipeline-development.md)
