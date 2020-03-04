---
title: Assembly di riferimento
description: Informazioni sugli assembly di riferimento, un tipo speciale di assembly in .NET che contengono solo la superficie dell'API pubblica della libreria
author: MSDN-WhiteKnight
ms.date: 09/12/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 3b85e51a015cca1e53ee2503c7bfa58c504fc718
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156465"
---
# <a name="reference-assemblies"></a>Assembly di riferimento

Gli *assembly di riferimento* sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie dell'API pubblica della libreria. Sono incluse le dichiarazioni per tutti i membri significativi quando si fa riferimento a un assembly negli strumenti di compilazione, ma si escludono tutte le implementazioni e le dichiarazioni dei membri privati che non hanno alcun impatto osservabile sul contratto API. Al contrario, gli assembly regolari vengono chiamati *assembly di implementazione*.

Gli assembly di riferimento non possono essere caricati per l'esecuzione, ma possono essere passati come input del compilatore nello stesso modo degli assembly di implementazione. Gli assembly di riferimento vengono in genere distribuiti con il Software Development Kit (SDK) di una particolare piattaforma o libreria.

L'uso di un assembly di riferimento consente agli sviluppatori di compilare programmi destinati a una versione specifica della libreria senza avere l'assembly di implementazione completo per tale versione. Si supponga di avere solo la versione più recente di una raccolta nel computer, ma si vuole compilare un programma destinato a una versione precedente di tale libreria. Se si esegue la compilazione direttamente nell'assembly di implementazione, si potrebbero usare inavvertitamente i membri dell'API che non sono disponibili nella versione precedente. Questo errore si verifica solo quando si esegue il test del programma nel computer di destinazione. Se si esegue la compilazione in base all'assembly di riferimento per la versione precedente, si otterrà immediatamente un errore in fase di compilazione.

Un assembly di riferimento può anche rappresentare un contratto, ovvero un set di API che non corrispondono all'assembly di implementazione concreto. Gli assembly di riferimento, detti *assembly del contratto*, possono essere usati per più piattaforme che supportano lo stesso set di API. Ad esempio, .NET Standard fornisce l'assembly del contratto, *netstandard. dll*, che rappresenta il set di API comuni condivise tra diverse piattaforme .NET. Le implementazioni di queste API sono contenute in assembly diversi su piattaforme diverse, ad esempio *mscorlib. dll* in .NET Framework o *System. private. CoreLib. dll* in .NET Core. Una libreria destinata a .NET Standard può essere eseguita in tutte le piattaforme che supportano .NET Standard.

## <a name="using-reference-assemblies"></a>Uso di assembly di riferimento

Per usare determinate API dal progetto, è necessario aggiungere riferimenti ai relativi assembly. È possibile aggiungere riferimenti a assembly di implementazione o a assembly di riferimento. È consigliabile usare gli assembly di riferimento ogni volta che sono disponibili. In questo modo si garantisce che vengano usati solo i membri dell'API supportati nella versione di destinazione, destinati a essere usati dagli strumenti di progettazione dell'API. L'uso dell'assembly di riferimento assicura che non si stiano prendendo una dipendenza dai dettagli di implementazione.

Gli assembly di riferimento per le librerie di .NET Framework vengono distribuiti con i targeting pack. È possibile ottenerli scaricando un programma di installazione autonomo o selezionando un componente nel programma di installazione di Visual Studio. Per ulteriori informazioni, vedere [Install the .NET Framework for Developers](../../framework/install/guide-for-developers.md). Per .NET Core e .NET Standard, gli assembly di riferimento vengono scaricati automaticamente in base alle necessità (tramite NuGet) e a cui si fa riferimento. Per .NET Core 3,0 e versioni successive, gli assembly di riferimento per il Framework di base sono inclusi nel pacchetto [Microsoft. NETCore. app. Ref](https://www.nuget.org/packages/Microsoft.NETCore.App.Ref) (il pacchetto [Microsoft. NETCore. app](https://www.nuget.org/packages/Microsoft.NETCore.App) viene usato in alternativa per le versioni precedenti a 3,0). Per altre informazioni, vedere [pacchetti, metapacchetti e Framework](../../core/packages.md) nella Guida di .NET Core.

Quando si aggiungono riferimenti a assembly .NET Framework in Visual Studio usando la finestra di dialogo **Aggiungi riferimento** , si seleziona un assembly dall'elenco e Visual Studio rileva automaticamente gli assembly di riferimento che corrispondono alla versione del Framework di destinazione selezionata nel progetto. Lo stesso vale per l'aggiunta di riferimenti direttamente al progetto MSBuild utilizzando l'elemento di progetto di [riferimento](/visualstudio/msbuild/common-msbuild-project-items#reference) : è sufficiente specificare il nome dell'assembly, non il percorso completo del file. Quando si aggiungono riferimenti a questi assembly nella riga di comando usando l'opzione del compilatore `-reference`[( C# in](../../csharp/language-reference/compiler-options/reference-compiler-option.md) e in [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md)) o usando il metodo <xref:Microsoft.CodeAnalysis.Compilation.AddReferences%2A?displayProperty=nameWithType> nell'API Roslyn, è necessario specificare manualmente i file di assembly di riferimento per la versione corretta della piattaforma di destinazione. .NET Framework file di assembly di riferimento si trovano negli *assembly di riferimento% ProgramFiles (x86)%\\\\Microsoft\\Framework\\. Directory NETFramework* . Per .NET Core, è possibile forzare l'operazione di pubblicazione per copiare gli assembly di riferimento per la piattaforma di destinazione nella sottodirectory *Publish/refs* della directory di output impostando la proprietà `PreserveCompilationContext` project su `true`. Quindi, è possibile passare questi file di assembly di riferimento al compilatore. L'uso di `DependencyContext` dal pacchetto [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/) può aiutare a individuare i percorsi.

Poiché non contengono alcuna implementazione, non è possibile caricare gli assembly di riferimento per l'esecuzione. il tentativo di eseguire questa operazione comporta un <xref:System.BadImageFormatException?displayProperty=nameWithType>. Tuttavia, possono comunque essere caricati nel contesto di sola reflection (usando il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType>), se è necessario esaminarne il contenuto.

## <a name="generating-reference-assemblies"></a>Generazione di assembly di riferimento

La generazione di assembly di riferimento per le librerie può essere utile quando gli utenti della libreria devono compilare i programmi rispetto a diverse versioni della libreria. La distribuzione degli assembly di implementazione per tutte queste versioni potrebbe risultare poco pratica a causa delle dimensioni elevate. Gli assembly di riferimento hanno dimensioni minori e la loro distribuzione come parte dell'SDK della libreria riduce le dimensioni del download e consente di risparmiare spazio su disco.

Gli IDE e gli strumenti di compilazione possono inoltre sfruttare gli assembly di riferimento per ridurre i tempi di compilazione in caso di soluzioni di grandi dimensioni costituite da più librerie di classi. In genere, negli scenari di compilazione incrementale un progetto viene ricompilato quando uno dei relativi file di input viene modificato, inclusi gli assembly da cui dipende. L'assembly di implementazione cambia ogni volta che il programmatore modifica l'implementazione di un membro. L'assembly di riferimento cambia solo quando è interessata l'API pubblica. Pertanto, l'utilizzo dell'assembly di riferimento come file di input anziché dell'assembly di implementazione consente di ignorare la compilazione del progetto dipendente in alcuni casi.

È possibile generare gli assembly di riferimento:

- In un progetto MSBuild, usando la [proprietà`ProduceReferenceAssembly` Project](/visualstudio/msbuild/common-msbuild-project-properties).
- Quando si compila il programma dalla riga di comando, da specifica[C#](../../csharp/language-reference/compiler-options/refonly-compiler-option.md) `-refonly` ( / [Visual Basic](../../visual-basic/reference/command-line-compiler/refonly-compiler-option.md) ) o[C#](../../csharp/language-reference/compiler-options/refout-compiler-option.md) `-refout` opzioni del compilatore ( / [Visual Basic](../../visual-basic/reference/command-line-compiler/refout-compiler-option.md)).
- Quando si usa l'API Roslyn, impostando <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.EmitMetadataOnly?displayProperty=nameWithType> su `true` e <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.IncludePrivateMembers?displayProperty=nameWithType> su `false` in un oggetto passato al metodo <xref:Microsoft.CodeAnalysis.Compilation.Emit%2A?displayProperty=nameWithType>.

Se si desidera distribuire gli assembly di riferimento con i pacchetti NuGet, è necessario includerli nella sottodirectory *ref\\* nella directory del pacchetto anziché nella sottodirectory *lib\\* utilizzata per gli assembly di implementazione.

## <a name="reference-assemblies-structure"></a>Struttura degli assembly di riferimento

Gli assembly di riferimento sono un'espansione del concetto correlato, *assembly di soli metadati*. Per gli assembly di soli metadati i corpi di metodo vengono sostituiti con un singolo corpo `throw null`, ma sono inclusi tutti i membri, tranne i tipi anonimi. Il motivo per l'uso di corpi `throw null` (in contrapposizione a nessun corpo) è in modo che **PEVerify** possa essere eseguito e superato (convalidando quindi la completezza dei metadati).

Gli assembly di riferimento rimuovono ulteriormente i metadati (membri privati) dagli assembly di soli metadati:

- Un assembly di riferimento include solo i riferimenti per i requisiti nella superficie dell'API. L'assembly reale può includere riferimenti aggiuntivi relativi a implementazioni specifiche. Ad esempio, l'assembly di riferimento per `class C { private void M() { dynamic d = 1; ... } }` non fa riferimento ad alcun tipo necessario per `dynamic`.
- I membri-funzione privati (metodi, proprietà ed eventi) vengono rimossi quando la rimozione non impatta in maniera visibile sulla compilazione. Se non sono presenti attributi [InternalsVisibleTo](xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute) , vengono rimossi anche i membri della funzione interna.

I metadati negli assembly di riferimento continuano a contenere le informazioni seguenti:

- Tutti i tipi, inclusi i tipi privati e annidati.
- Tutti gli attributi, anche quelli interni.
- Tutti i metodi virtuali.
- Implementazioni esplicite dell'interfaccia.
- Proprietà ed eventi implementati in modo esplicito perché le relative funzioni di accesso sono virtuali.
- Tutti i campi di strutture.

Gli assembly di riferimento includono un attributo [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) a livello di assembly. Questo attributo può essere specificato nell'origine. il compilatore non dovrà quindi sintetizzarlo. A causa di questo attributo, i runtime rifiuteranno di caricare gli assembly di riferimento per l'esecuzione, ma possono essere caricati in modalità di sola reflection.

I dettagli della struttura di assembly di riferimento esatti dipendono dalla versione del compilatore. Le versioni più recenti possono scegliere di escludere un numero maggiore di metadati se è determinato come non influire sulla superficie dell'API pubblica.

> [!NOTE]
> Le informazioni contenute in questa sezione sono valide solo per gli assembly di riferimento generati dai compilatori Roslyn a partire dalla C# versione 7,1 o Visual Basic versione 15,3. La struttura degli assembly di riferimento per le librerie .NET Framework e .NET Core può differire in alcuni dettagli, perché usano il proprio meccanismo di generazione di assembly di riferimento. Ad esempio, possono avere corpi del metodo completamente vuoti anziché il corpo del `throw null`. Tuttavia, il principio generale si applica comunque: non hanno implementazioni del metodo utilizzabili e contengono metadati solo per i membri che hanno un effetto osservabile da una prospettiva API pubblica.

## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](index.md)
- [Panoramica sull'impostazione dei framework di destinazione](/visualstudio/ide/visual-studio-multi-targeting-overview)
- [Procedura: aggiungere o rimuovere riferimenti tramite Gestione riferimenti](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)
