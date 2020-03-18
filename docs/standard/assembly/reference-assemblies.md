---
title: Assembly di riferimento
description: Informazioni sugli assembly di riferimento, un tipo speciale di assembly in .NET che contengono solo la superficie API pubblica della libreria
author: MSDN-WhiteKnight
ms.date: 09/12/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 938942caf81c54a8aa9207dbe87559438ffb252e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79141068"
---
# <a name="reference-assemblies"></a>Assembly di riferimento

*Gli assembly* di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie API pubblica della libreria. Includono dichiarazioni per tutti i membri che sono significative quando si fa riferimento a un assembly negli strumenti di compilazione, ma escludono tutte le implementazioni dei membri e le dichiarazioni di membri privati che non hanno alcun impatto osservabile sul contratto API. Al contrario, gli assembly regolari sono denominati assembly di *implementazione.*

Gli assembly di riferimento non possono essere caricati per l'esecuzione, ma possono essere passati come input del compilatore nello stesso modo degli assembly di implementazione. Gli assembly di riferimento vengono in genere distribuiti con il Software Development Kit (SDK) di una determinata piattaforma o libreria.

L'utilizzo di un assembly di riferimento consente agli sviluppatori di compilare programmi destinati a una versione specifica della libreria senza disporre dell'assembly di implementazione completo per tale versione. Si supponga di disporre solo della versione più recente di alcune librerie nel computer, ma si desidera compilare un programma destinato a una versione precedente di tale libreria. Se si esegue la compilazione direttamente in base all'assembly di implementazione, è possibile utilizzare inavvertitamente membri API non disponibili nella versione precedente. Questo errore si trova solo durante il test del programma sul computer di destinazione. Se si esegue la compilazione in base all'assembly di riferimento per la versione precedente, verrà immediatamente visualizzato un errore in fase di compilazione.

Un assembly di riferimento può anche rappresentare un contratto, ovvero un set di API che non corrispondono all'assembly di implementazione concreto. Tali assembly di riferimento, denominati assembly del *contratto*, possono essere utilizzati per indirizzare più piattaforme che supportano lo stesso set di API. Ad esempio, .NET Standard fornisce l'assembly del contratto, *netstandard.dll*, che rappresenta il set di API comuni condivise tra piattaforme .NET diverse. Le implementazioni di queste API sono contenute in assembly diversi su piattaforme diverse, ad esempio *mscorlib.dll* in .NET Framework o *System.Private.CoreLib.dll* in .NET Core. A library that targets .NET Standard can run on all platforms that support .NET Standard.

## <a name="using-reference-assemblies"></a>Utilizzo di assembly di riferimento

Per utilizzare determinate API del progetto, è necessario aggiungere riferimenti ai relativi assembly. È possibile aggiungere riferimenti a assembly di implementazione o fare riferimento ad assembly. Si consiglia di utilizzare gli assembly di riferimento ogni volta che sono disponibili. In questo modo si garantisce che si sta utilizzando solo i membri API supportati nella versione di destinazione, destinato a essere utilizzato dai progettisti di API. L'utilizzo dell'assembly di riferimento garantisce che non si assa una dipendenza dai dettagli di implementazione.

Gli assembly di riferimento per le librerie di .NET Framework vengono distribuiti con i pacchetti di destinazione. È possibile ottenerli scaricando un programma di installazione autonomo o selezionando un componente nel programma di installazione di Visual Studio.You can obtain them by downloading a standalone installer or by selecting a component in Visual Studio installer. Per ulteriori informazioni, vedere [Installare .NET Framework per gli sviluppatori.](../../framework/install/guide-for-developers.md) Per .NET Core e .NET Standard, gli assembly di riferimento vengono scaricati automaticamente in base alle esigenze (tramite NuGet) e a cui viene fatto riferimento. Per .NET Core 3.0 e versioni successive, gli assembly di riferimento per il framework di base sono nel pacchetto [Microsoft.NETCore.App.Ref](https://www.nuget.org/packages/Microsoft.NETCore.App.Ref) (il pacchetto [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) viene usato invece per le versioni precedenti alla 3.0). Per altre informazioni, vedere pacchetti, metapacchetti e framework nella Guida di .NET Core.For more information, see [Packages, metapackages, and frameworks](../../core/packages.md) in the .NET Core Guide.

Quando si aggiungono riferimenti agli assembly .NET Framework in Visual Studio utilizzando la finestra di dialogo **Aggiungi riferimento,** si seleziona un assembly dall'elenco e Visual Studio trova automaticamente gli assembly di riferimento che corrispondono alla versione del framework di destinazione selezionata nel progetto. Lo stesso vale per l'aggiunta di riferimenti direttamente nel progetto MSBuild usando l'elemento di progetto [di riferimento:](/visualstudio/msbuild/common-msbuild-project-items#reference) è sufficiente specificare il nome dell'assembly, non il percorso completo del file. Quando si aggiungono riferimenti a questi assembly `-reference` nella riga di comando utilizzando l'opzione del compilatore ([in C , in C ,](../../csharp/language-reference/compiler-options/reference-compiler-option.md) e in [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md)) o utilizzando il <xref:Microsoft.CodeAnalysis.Compilation.AddReferences%2A?displayProperty=nameWithType> metodo nell'API Roslyn , è necessario specificare manualmente i file di assembly di riferimento per la versione della piattaforma di destinazione corretta. I file degli assembly di riferimento di .NET Framework si trovano nella cartella *%ProgramFiles(x86)%\\Reference Assemblies\\Microsoft\\Framework\\. directory NETFramework.* Per .NET Core, è possibile forzare l'operazione di pubblicazione per copiare gli assembly di `PreserveCompilationContext` riferimento `true`per la piattaforma di destinazione nella sottodirectory *publish/refs* della directory di output impostando la proprietà del progetto su . È quindi possibile passare questi file di assembly di riferimento al compilatore. L'utilizzo `DependencyContext` dal pacchetto [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/) consente di individuare i relativi percorsi.

Poiché non contengono alcuna implementazione, gli assembly di riferimento non possono essere caricati per l'esecuzione. Cercando di farlo risultati <xref:System.BadImageFormatException?displayProperty=nameWithType>in un file . Se si desidera esaminare il contenuto di un assembly di riferimento, è possibile caricarlo nel contesto solo reflection in .NET Framework (utilizzando il <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> metodo ) o <xref:System.Reflection.MetadataLoadContext> in in .NET Core.

## <a name="generating-reference-assemblies"></a>Generazione di assembly di riferimento

La generazione di assembly di riferimento per le librerie può essere utile quando gli utenti della libreria devono compilare i programmi in base a molte versioni diverse della libreria. La distribuzione degli assembly di implementazione per tutte queste versioni potrebbe risultare poco pratica a causa delle dimensioni grandi. Gli assembly di riferimento hanno dimensioni inferiori e la distribuzione come parte dell'SDK della libreria riduce le dimensioni del download e consente di risparmiare spazio su disco.

Gli IDE e gli strumenti di compilazione possono inoltre sfruttare gli assembly di riferimento per ridurre i tempi di compilazione in caso di soluzioni di grandi dimensioni costituite da più librerie di classi. In genere, negli scenari di compilazione incrementale un progetto viene ricompilato quando viene modificato uno dei relativi file di input, inclusi gli assembly da cui dipende. L'assembly dell'implementazione cambia ogni volta che il programmatore modifica l'implementazione di qualsiasi membro. L'assembly di riferimento cambia solo quando è interessata l'API pubblica. Pertanto, l'utilizzo dell'assembly di riferimento come file di input anziché come assembly di implementazione consente in alcuni casi di ignorare la compilazione del progetto dipendente.

È possibile generare assiemi di riferimento:

- In un progetto MSBuild, utilizzando la [ `ProduceReferenceAssembly` proprietà](/visualstudio/msbuild/common-msbuild-project-properties)del progetto .
- Durante la compilazione del programma dalla riga `-refonly` di comando, specificando `-refout` le opzioni del compilatore[(C ,](../../csharp/language-reference/compiler-options/refonly-compiler-option.md) / Visual[Basic](../../visual-basic/reference/command-line-compiler/refonly-compiler-option.md) ) o ( C[.](../../csharp/language-reference/compiler-options/refout-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refout-compiler-option.md)).
- Quando si usa l'API <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.EmitMetadataOnly?displayProperty=nameWithType> `true` Roslyn, impostando su e <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.IncludePrivateMembers?displayProperty=nameWithType> `false` su in un oggetto passato al <xref:Microsoft.CodeAnalysis.Compilation.Emit%2A?displayProperty=nameWithType> metodo.

Se si desidera distribuire gli assembly di riferimento con i pacchetti NuGet, è necessario includerli nella sottodirectory *ref\\ * nella directory del pacchetto anziché nella sottodirectory *lib\\ * utilizzata per gli assembly di implementazione.

## <a name="reference-assemblies-structure"></a>Struttura degli assiemi di riferimento

Gli assembly di riferimento sono un'espansione del concetto correlato, *gli assembly di soli metadati*. Per gli assembly di soli metadati i corpi di metodo vengono sostituiti con un singolo corpo `throw null`, ma sono inclusi tutti i membri, tranne i tipi anonimi. Il motivo `throw null` per l'utilizzo di corpi (al contrario di nessun corpo) è in modo che **PEVerify** può essere eseguito e passato (convalidando così la completezza dei metadati).

Gli assembly di riferimento rimuovono ulteriormente i metadati (membri privati) dagli assembly di soli metadati:

- Un assembly di riferimento include solo i riferimenti per i requisiti nella superficie dell'API. L'assembly reale può includere riferimenti aggiuntivi relativi a implementazioni specifiche. Ad esempio, l'assembly di riferimento per `class C { private void M() { dynamic d = 1; ... } }` `dynamic`non fa riferimento ai tipi necessari per .
- I membri-funzione privati (metodi, proprietà ed eventi) vengono rimossi quando la rimozione non impatta in maniera visibile sulla compilazione. Se non sono presenti attributi [InternalsVisibleTo,](xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute) vengono rimossi anche i membri funzione interni.

I metadati negli assembly di riferimento continuano a mantenere le seguenti informazioni:

- Tutti i tipi, inclusi i tipi privati e annidati.
- Tutti gli attributi, anche quelli interni.
- Tutti i metodi virtuali.
- Implementazioni esplicite dell'interfaccia.
- Proprietà ed eventi implementati in modo esplicito, perché le relative funzioni di accesso sono virtuali.
- Tutti i campi delle strutture.

Gli assembly di riferimento includono un attributo [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) a livello di assembly. Questo attributo può essere specificato nell'origine; quindi il compilatore non avrà bisogno di sintetizzarlo. A causa di questo attributo, i runtime rifiuteranno di caricare gli assembly di riferimento per l'esecuzione (ma possono essere caricati in modalità solo reflection).

I dettagli della struttura dell'assembly di riferimento dipendono direttamente dalla versione del compilatore. Le versioni più recenti possono scegliere di escludere più metadati se viene determinato come non influisce sulla superficie dell'API pubblica.

> [!NOTE]
> Le informazioni contenute in questa sezione sono applicabili solo agli assembly generati dai compilatori Roslyn a partire dalla versione 7.1 o da Visual Basic versione 15.3. La struttura degli assembly di riferimento per le librerie .NET Framework e .NET Core può differire in alcuni dettagli, perché utilizzano il proprio meccanismo di generazione di assembly di riferimento. Ad esempio, potrebbero avere corpi di `throw null` metodo completamente vuoti anziché il corpo. Ma il principio generale si applica ancora: non hanno implementazioni di metodo utilizzabili e contengono metadati solo per i membri che hanno un impatto osservabile da una prospettiva API pubblica.

## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](index.md)
- [Panoramica sull'impostazione dei framework di destinazione](/visualstudio/ide/visual-studio-multi-targeting-overview)
- [Procedura: aggiungere o rimuovere riferimenti tramite Gestione riferimenti](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)
