---
title: Generazione e compilazione di codice sorgente a partire da un grafo CodeDOM
description: Generare e compilare codice sorgente da un grafo CodeDOM in .NET. Utilizzare un provider di codice CodeDOM per generare codice sorgente e compilare assembly.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
ms.openlocfilehash: 85654fe961f01ad7b8fb886d59a3de9ab0efe7aa
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474046"
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a>Generazione e compilazione di codice sorgente a partire da un grafo CodeDOM
Lo spazio dei nomi <xref:System.CodeDom.Compiler> offre le interfacce per la generazione di codice sorgente da oggetti grafici CodeDOM e per la gestione della compilazione con i compilatori supportati. Un provider di codice può generare codice sorgente in un determinato linguaggio di programmazione in base a un grafo CodeDOM. Una classe che deriva da <xref:System.CodeDom.Compiler.CodeDomProvider> in genere consente l'uso di metodi per la generazione e la compilazione di codice per il linguaggio supportato dal provider.  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a>Usare un provider di codice CodeDOM per generare codice sorgente  
 Per generare codice sorgente in un determinato linguaggio, è necessario un grafo CodeDOM che rappresenti la struttura del codice sorgente da generare.  
  
 Nell'esempio seguente viene illustrato come creare un'istanza di <xref:Microsoft.CSharp.CSharpCodeProvider>:  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 Il grafo per la generazione di codice è solitamente contenuto in un oggetto <xref:System.CodeDom.CodeCompileUnit>. Per generare codice per un oggetto **CodeCompileUnit** contenente un grafo CodeDOM, chiamare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> del provider di codice. Questo metodo ha un parametro per un oggetto <xref:System.IO.TextWriter> che usa per generare il codice sorgente, quindi in alcuni casi è necessario creare innanzitutto un oggetto **TextWriter** in cui si può scrivere. L'esempio seguente illustra la generazione di codice da **CodeCompileUnit** e la scrittura del codice sorgente generato in un file denominato HelloWorld.cs.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a>Usare un provider di codice CodeDOM per compilare assembly  
 **Chiamata della compilazione**  
  
 Per compilare un assembly usando un provider CodeDom, è necessario che il codice sorgente da compilare sia scritto in un linguaggio per il quale è disponibile un compilatore oppure usare un grafo CodeDOM da cui può essere generato il codice da compilare.  
  
 Se si esegue la compilazione da un grafo CodeDOM, passare l'oggetto <xref:System.CodeDom.CodeCompileUnit> contenente il grafo al metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> del provider di codice. Se si usa un file di codice sorgente in un linguaggio accettato dal compilatore, passare il nome del file contenente il codice sorgente al metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> del provider CodeDom. È anche possibile passare una stringa contenente il codice sorgente in un linguaggio accettato dal compilatore al metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> del provider CodeDom.  
  
 **Configurazione dei parametri di compilazione**  
  
 Tutti i metodi di chiamata della compilazione standard di un provider CodeDom hanno un parametro di tipo <xref:System.CodeDom.Compiler.CompilerParameters> che indica le opzioni da usare per la compilazione.  
  
 È possibile specificare un nome di file per l'assembly di output nella proprietà <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> di **CompilerParameters**. In caso contrario, verrà usato un nome di file di output predefinito.  
  
 Per impostazione predefinita, un nuovo oggetto **CompilerParameters** viene inizializzato con la relativa proprietà <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> impostata su **false**. Se si compila un programma eseguibile, è necessario impostare la proprietà **GenerateExecutable** su **true**. Quando il **GenerateExecutable** è impostato su **false**, il compilatore genera una libreria di classi.  
  
 Se si compila un file eseguibile da un grafo CodeDOM, è necessario definire un oggetto <xref:System.CodeDom.CodeEntryPointMethod> nel grafo. Se esistono più punti di ingresso del codice, può essere necessario impostare la proprietà <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> di **CompilerParameters** sul nome della classe che definisce il punto di ingresso da usare.  
  
 Per includere le informazioni di debug in un file eseguibile generato, impostare la proprietà <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> su **true**.  
  
 Se il progetto fa riferimento ad assembly, è necessario specificare i nomi degli assembly come elementi di un oggetto <xref:System.Collections.Specialized.StringCollection> come la proprietà <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> dell'oggetto **CompilerParameters** usato per la chiamata della compilazione.  
  
 È possibile compilare un assembly scritto nella memoria anziché su disco impostando la proprietà <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> su **true**. Quando un assembly viene generato nella memoria, il codice può ottenere un riferimento all'assembly generato dalla proprietà <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> di un oggetto <xref:System.CodeDom.Compiler.CompilerResults>. Se un assembly viene scritto su disco, è possibile ottenere il percorso all'assembly generato dalla proprietà <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> di un oggetto **CompilerResults**.  
  
 Per specificare una stringa di argomenti della riga di comando personalizzati da usare quando si richiama il processo di compilazione, impostare la stringa nella proprietà <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>.  
  
 Se è necessario un token di sicurezza Win32 per richiamare il processo di compilazione, specificare il token nella proprietà <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>.  
  
 Per collegare un file di risorse Win32 nell'assembly compilato, specificare il nome del file nella proprietà <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>.  
  
 Per specificare un livello di avviso per l'interruzione della compilazione, impostare la proprietà <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> su un intero che rappresenti il livello di avviso in corrispondenza del quale verrà interrotta la compilazione. È anche possibile configurare il compilatore in modo che interrompa la compilazione se vengono rilevati avvisi impostando la proprietà <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> su **true**.  
  
 Nell'esempio di codice seguente viene illustrata la compilazione di un file di origine usando un provider CodeDom derivato dalla classe <xref:System.CodeDom.Compiler.CodeDomProvider>.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a>Linguaggi con supporto iniziale  
 Con .NET Framework vengono forniti compilatori e generatori di codice per i seguenti linguaggi: C#, Visual Basic, C++ e JScript. Il supporto CodeDOM può essere esteso ad altri linguaggi implementando generatori di codice specifici del linguaggio e compilatori di codice.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- [Generazione e compilazione dinamica di codice sorgente](dynamic-source-code-generation-and-compilation.md)
- [Riferimento rapido per CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))
