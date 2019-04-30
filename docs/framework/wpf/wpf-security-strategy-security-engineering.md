---
title: Strategia di sicurezza WPF - Progettazione della sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: 27258110a8852c00990d73cd9ca8685c3ead315d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053834"
---
# <a name="wpf-security-strategy---security-engineering"></a>Strategia di sicurezza WPF - Progettazione della sicurezza
Trustworthy Computing è un'iniziativa Microsoft per garantire la produzione di codice sicuro. Un elemento chiave dell'iniziativa Trustworthy Computing è [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)]. [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] è una procedura di progettazione usata insieme a processi di progettazione standard per semplificare la generazione di codice sicuro. [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] prevede dieci fasi che combinano procedure consigliate con formalizzazione, misurabilità e struttura aggiuntiva, tra cui:  
  
- Analisi della progettazione della sicurezza  
  
- Controlli di qualità basati su strumenti  
  
- Test di penetrazione  
  
- Revisione finale della sicurezza  
  
- Gestione della sicurezza dei prodotti in seguito al rilascio  
  
## <a name="wpf-specifics"></a>Specifiche di WPF  
 Il team di progettazione di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applica ed estende [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], la combinazione dei quali include i fattori chiave seguenti:  
  
 [Classificazione dei rischi](#threat_modeling)  
  
 [Analisi della sicurezza e strumenti di modifica](#tools)  
  
 [Tecniche di test](#techniques)  
  
 [Gestione del codice critico](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a>Classificazione dei rischi  
 La classificazione dei rischi è un componente centrale di [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] e viene usata per profilare un sistema in modo da determinare le potenziali vulnerabilità della sicurezza. Una volta identificate le vulnerabilità, la classificazione dei rischi garantisce anche che vengano attuate le misure di prevenzione appropriate.  
  
 A livello generale, la classificazione dei rischi comporta i passaggi principali seguenti, in cui viene usato un negozio di alimentari come esempio:  
  
1. **Identificazione degli asset**. Gli asset di un negozio di alimentari potrebbero includere i dipendenti, una cassaforte, i registri di cassa e l'inventario.  
  
2. **Enumerazione dei punti di ingresso**. I punti di ingresso di un negozio di alimentari potrebbero includere gli ingressi anteriore e posteriore, le finestre, la rampa di carico e i condizionatori d'aria.  
  
3. **Esame degli attacchi contro asset e punti di ingresso**. Un possibile attacco potrebbe avere come oggetto la *cassa* del negozio di alimentari attraverso il punto di ingresso *condizionatore d'aria*. L'impianto potrebbe essere smontato per fare passare la cassa attraverso il muro fino all'esterno del negozio.  
  
 La classificazione dei rischi viene applicata in tutto [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] e include:  
  
- Modo in cui il parser [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] legge i file, esegue il mapping del testo alle classi del modello a oggetti corrispondenti e crea il codice effettivo.  
  
- Modo in cui un handle di finestra (hWnd) viene creato, invia messaggi ed è usato per il rendering del contenuto di una finestra.  
  
- Modo in cui il data binding ottiene risorse e interagisce con il sistema.  
  
 Questi modelli di classificazione dei rischi sono importanti per identificare i requisiti di progettazione della sicurezza e le misure di prevenzione dei rischi durante il processo di sviluppo.  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a>Analisi del codice sorgente e strumenti di modifica  
 Oltre agli elementi di revisione manuale del codice di sicurezza di [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], il team di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] usa diversi strumenti per l'analisi del codice sorgente e le modifiche associate in modo da ridurre le vulnerabilità della sicurezza. Viene usata un'ampia gamma di strumenti di origine, tra cui:  
  
- **FXCop**: Trova i problemi di sicurezza comuni nel codice gestito che vanno dalle regole di ereditarietà all'utilizzo di sicurezza di accesso di codice come garantire un'interoperabilità sicura con codice non gestito al. Vedere [FxCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29).  
  
- **Prefix/Prefast**: Trova le vulnerabilità di sicurezza e problemi di sicurezza comuni nel codice non gestito, ad esempio i sovraccarichi del buffer, i problemi di stringa di formato e il controllo degli errori.  
  
- **Utilizzo API escluso**: Cerca nel codice per individuare l'utilizzo accidentale di funzioni che sono note provocare problemi di sicurezza, come sorgente `strcpy`. Una volta identificate, queste funzioni vengono sostituite con alternative più sicure.  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a>Tecniche di test  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] usa svariate tecniche di test della sicurezza, tra cui:  
  
- **Whitebox Testing**: I tester visualizzano il codice sorgente e quindi compilano test per gli exploit  
  
- **Blackbox Testing**: I tester provano a trovare exploit di sicurezza esaminando l'API e le funzionalità e quindi tentano di attaccare il prodotto.  
  
- **Problemi di sicurezza di regressione da altri prodotti**: In cui è possibile, vengono testati i problemi di sicurezza di prodotti correlati. Ad esempio, sono state identificate e provate le varianti appropriate di circa 60 problemi di sicurezza per [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] per verificarne l'applicabilità a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].  
  
- **Test di penetrazione basati su strumenti tramite test con dati casuali File**: File test con dati casuali è che l'uso di un lettore di file di input intervallo tramite un'ampia gamma di input. Un esempio in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] in cui viene usata questa tecnica consiste nel verificare la presenza di errori nel codice di decodifica delle immagini.  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a>Gestione del codice critico  
 Per la [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] compila una sandbox di sicurezza utilizzando il supporto di .NET Framework per contrassegnare e verificare il codice critico per la sicurezza che eleva i privilegi (vedere **metodologia critica per la sicurezza** in [WPF Strategia di sicurezza - sicurezza della piattaforma](wpf-security-strategy-platform-security.md)). A causa degli elevati requisiti di qualità per il codice critico per la sicurezza, tale codice riceve un livello aggiuntivo di controllo della gestione del codice sorgente e della sicurezza. All'incirca dal 5% al 10% di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] è costituito da codice critico per la sicurezza, esaminato da un team di revisione dedicato. Il codice sorgente e il processo di archiviazione vengono gestiti verificando il codice critico per la sicurezza ed eseguendo il mapping di ogni entità critica (ovvero un metodo che contiene codice critico) al rispettivo stato di approvazione. Lo stato di approvazione include i nomi di uno o più revisori. Ogni compilazione giornaliera di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] confronta il codice critico con quello delle compilazioni precedenti per verificare la presenza di eventuali modifiche non approvate. Se un tecnico modifica codice critico senza l'approvazione del team di revisione, il codice viene identificato e corretto immediatamente. Questo processo permette l'applicazione e la gestione di un livello particolarmente elevato di controllo sul codice sandbox di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza](security-wpf.md)
- [Sicurezza con attendibilità parziale in WPF](wpf-partial-trust-security.md)
- [Strategia di sicurezza di WPF - Sicurezza della piattaforma](wpf-security-strategy-platform-security.md)
- [Trustworthy Computing](https://www.microsoft.com/mscorp/twc/default.mspx)
- [Sicurezza in .NET](../../standard/security/index.md)
