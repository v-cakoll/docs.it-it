---
title: Introduzione di .NET Native
ms.date: 03/30/2017
ms.assetid: fc9e04e8-2d05-4870-8cd6-5bd276814afc
ms.openlocfilehash: 1c0c25ddf379c31a9c7b4437d36e7e0cbf1bb2f3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128406"
---
# <a name="getting-started-with-net-native"></a>Introduzione di .NET Native

È possibile seguire le stesse procedure sia che si stia scrivendo una nuova app di Windows per Windows 10 sia che si stia migrando un'app di Windows Store esistente. Per creare un'app .NET Native, seguire questa procedura:

1. [Sviluppare un'app UWP (Universal Windows Platform) per Windows 10](#Step1)e testare le build di debug dell'app per verificarne il corretto funzionamento.

2. [Gestire la reflection aggiuntiva e l'uso della serializzazione](#Step2).

3. [Distribuire e testare le build di rilascio dell'app](#Step3).

4. [Risolvere manualmente i metadati mancanti](#Step4)e ripetere il [passaggio 3](#Step3) finché non vengono risolti tutti i problemi.

> [!NOTE]
> Se si esegue la migrazione di un'app di Windows Store esistente a .NET Native, assicurarsi di consultare la pagina relativa alla [migrazione dell'app di Windows Store a .NET native](migrating-your-windows-store-app-to-net-native.md).

<a name="Step1"></a>

## <a name="step-1-develop-and-test-debug-builds-of-your-uwp-app"></a>Passaggio 1: Sviluppare e testare le build di debug dell'app UWP

Per sviluppare una nuova app ed eseguire la migrazione di un'app esistente, si segue lo stesso processo usato per una qualsiasi app di Windows.

1. Creare un nuovo progetto UWP in Visual Studio usando il modello dell'app di Windows universale per Visual C# o Visual Basic. Per impostazione predefinita, tutte le applicazioni UWP sono destinate a CoreCLR e le relative build di rilascio vengono compilate usando la catena di strumenti .NET Native.

2. Sono presenti alcuni problemi noti di compatibilità tra i progetti di app UWP compilati con o senza la catena di strumenti .NET Native. Per altre informazioni, vedere la [guida alla migrazione](migrating-your-windows-store-app-to-net-native.md) .

È ora possibile scrivere codice C# o Visual Basic sulla superficie di attacco .NET Native in esecuzione nel sistema locale (o nel simulatore).

> [!IMPORTANT]
> Quando si sviluppa l'app, annotare qualsiasi uso di serializzazione o reflection nel codice.

Per impostazione predefinita, le compilazioni di debug vengono compilate tramite JIT per consentire la distribuzione rapida F5, mentre le build di rilascio vengono compilate utilizzando la .NET Native tecnologia di pre-compilazione. Quindi, è necessario compilare e testare le build di debug dell'app per verificarne il normale funzionamento prima di compilarle con la catena di strumenti .NET Native.

<a name="Step2"></a>

## <a name="step-2-handle-additional-reflection-and-serialization-usage"></a>Passaggio 2: Gestire l'uso aggiuntivo della reflection e della serializzazione

Default.rd.xml, il file di direttive di runtime, aggiunto automaticamente al progetto al momento della creazione, si trova nella cartella **Proprietà** del progetto se si sviluppa in C#, nella cartella **Progetto personale** del progetto se si sviluppa in Visual Basic.

> [!NOTE]
> Per una panoramica del processo di compilazione di .NET Native e informazioni di base sui motivi per cui è necessario un file di direttive di runtime, vedere [Compilazione e .NET Native](net-native-and-compilation.md).

Il file di direttive di runtime viene usato per definire i metadati necessari all'app in fase di esecuzione. In alcuni casi, la versione predefinita del file potrebbe essere sufficiente. Tuttavia, il codice che si basa sulla serializzazione o la reflection potrebbe richiedere voci aggiuntive nei file di direttive di runtime.

**Serializzazione**

Esistono due categorie di serializzatori ed entrambe possono richiedere voci aggiuntive nel file di direttive di runtime:

- Serializzatori non basati sulla reflection. I serializzatori nella libreria di classi .NET Framework, ad esempio le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>e <xref:System.Xml.Serialization.XmlSerializer> , non si basano sulla reflection. Tuttavia, richiedono che il codice venga generato in base all'oggetto da serializzare o deserializzare.  Per altre informazioni, vedere la sezione "Serializzatori Microsoft" in [Serialization and Metadata](serialization-and-metadata.md).

- Serializzatori di terze parti. Le librerie di serializzazione di terze parti, la più comune delle quali è il serializzatore JSON di Newtonsoft, sono generalmente basate sulla reflection e richiedono voci nel \* file. Rd. XML per supportare la serializzazione e la deserializzazione degli oggetti. Per altre informazioni, vedere la sezione "Serializzatori di terze parti" in [Serialization and Metadata](serialization-and-metadata.md).

**Metodi basati sulla reflection**

In alcuni casi, l'uso della reflection nel codice non è scontato. Alcuni modelli di programmazione o API comuni non sono considerati parte dell'API di reflection ma si basano sulla reflection per una corretta esecuzione Sono inclusi i seguenti metodi di creazione di un'istanza del tipo di costruzione del metodo:

- Metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>

- Metodi <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> e <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>

- Metodo <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> .

Per altre informazioni, vedere [APIs That Rely on Reflection](apis-that-rely-on-reflection.md).

> [!NOTE]
> I nomi dei tipi usati nei file di direttive di runtime devono essere completi. Ad esempio, il file deve specificare "System.String" invece di "String".

<a name="Step3"></a>

## <a name="step-3-deploy-and-test-the-release-builds-of-your-app"></a>Passaggio 3: Distribuire e testare le build di rilascio dell'app

Dopo aver aggiornato il file di direttive di runtime, è possibile ricompilare e distribuire le build di rilascio dell'app. .NET Native file binari vengono inseriti nella sottodirectory ILC. out della directory specificata nella casella di testo **percorso output di compilazione** della finestra di dialogo **Proprietà** del progetto, scheda **Compila** . i file binari non inclusi in questa cartella non sono stati compilati con .NET native. Testare accuratamente l'app e tutti gli scenari, inclusi gli scenari di errore, in ogni piattaforma di destinazione.

Se l'app non funziona correttamente (in particolare se genera eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) o [MissingInteropDataException](missinginteropdataexception-class-net-native.md) in runtime), seguire le istruzioni della sezione successiva [Passaggio 4: Risolvere manualmente i metadati mancanti](#Step4). L'abilitazione di eccezioni first-chance aiuta a individuare i bug.

Quando sono state testate e sottoposte a debug le build di debug dell'app e si è certi di aver eliminato le eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) e [MissingInteropDataException](missinginteropdataexception-class-net-native.md) , è consigliabile testare l'app come un'app ottimizzata .NET native. Per eseguire questa operazione, modificare la configurazione del progetto attiva da **Debug** a **Rilascio**.

<a name="Step4"></a>

## <a name="step-4-manually-resolve-missing-metadata"></a>Passaggio 4: Risolvere manualmente i metadati mancanti

L'errore più comune che si verificherà con .NET Native che non si verificano sul desktop è un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)o [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) in fase di esecuzione. In alcuni casi, l'assenza di metadati può causare un comportamento imprevisto o anche errori dell'app. In questa sezione viene descritto come eseguire il debug e risolvere tali eccezioni aggiungendo delle direttive al file di direttive di runtime. Per informazioni sul formato delle direttive di runtime, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md). Dopo aver aggiunto le direttive di runtime, [distribuire e testare di nuovo l'app](#Step3) e risolvere le eventuali nuove eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)e  [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) finché non ne vengono generate più.

> [!TIP]
> Specificare le direttive di runtime a un alto livello per rendere l'app adattabile alle modifiche del codice.  Si consiglia di aggiungere le direttive di runtime a livello degli spazi dei nomi e dei tipi e non a livello dei membri. Potrebbe essere necessario un compromesso tra resilienza, file binari di grandi dimensioni e tempi di compilazione più lunghi.

Quando si risolve un'eccezione relativa a metadati mancanti, prendere in considerazione quanto segue:

- Che cosa stava tentando di eseguire l'app prima dell'eccezione?

  - Ad esempio, stava eseguendo il data binding, la serializzazione o la deserializzazione dei dati o usando direttamente l'API reflection?

- Si tratta di un caso isolato o si ritiene che possa verificarsi lo stesso problema anche per altri tipi?

  - Ad esempio, un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md) viene generata durante la serializzazione di un tipo nel modello a oggetti dell'app.  Se si conoscono gli altri tipi da serializzare, è possibile aggiungere contemporaneamente le direttive di runtime per questi tipi (o per gli spazi dei nomi che li contengono, a seconda di quanto efficacemente è organizzato il codice).

- È possibile riscrivere il codice in modo che non usi la reflection?

  - Ad esempio, il codice usa la parola chiave `dynamic` quando si conosce il tipo previsto?

  - Il codice chiama un metodo basato sulla reflection quando è disponibile un'alternativa migliore?

> [!NOTE]
> Per ulteriori informazioni sulla gestione dei problemi derivanti dalle differenze nella reflection e sulla disponibilità dei metadati nelle app desktop e .NET Native, vedere [API basate sulla reflection](apis-that-rely-on-reflection.md).

Per alcuni esempi specifici di gestione delle eccezioni e di altri problemi relativi ai test dell'app, vedere:

- [Esempio: Gestione delle eccezioni durante il data binding](example-handling-exceptions-when-binding-data.md)

- [Esempio: Risoluzione dei problemi di programmazione dinamica](example-troubleshooting-dynamic-programming.md)

- [Eccezioni di runtime in app .NET](runtime-exceptions-in-net-native-apps.md)

## <a name="see-also"></a>Vedi anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Installazione e configurazione di .NET Native](https://docs.microsoft.com/previous-versions/dn600164(v=vs.110))
- [Compilazione e .NET Native](net-native-and-compilation.md)
- [Reflection e .NET Native](reflection-and-net-native.md)
- [API basate sulla reflection](apis-that-rely-on-reflection.md)
- [Serializzazione e metadati](serialization-and-metadata.md)
- [Migrazione dell'app di Windows Store a .NET Native](migrating-your-windows-store-app-to-net-native.md)
