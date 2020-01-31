---
title: Documentazione del codice con i commenti XML
description: Informazioni su come documentare il codice con commenti della documentazione XML e generare un file di documentazione XML in fase di compilazione.
ms.date: 01/21/2020
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: ef0d22e0ee7faa3ba51da6b44cf1827f19baf4f1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787828"
---
# <a name="document-your-code-with-xml-comments"></a>Documentare il codice con commenti XML

I commenti in formato documentazione XML sono commenti speciali, aggiunti alla definizione di ogni tipo o membro definito dall'utente.
Sono speciali perché possono essere elaborati dal compilatore per generare un file di documentazione XML in fase di compilazione.
Il file XML generato dal compilatore può essere distribuito insieme agli assembly .NET in modo che Visual Studio e altri IDE possano usare IntelliSense per visualizzare informazioni rapide su tipi o membri. È anche possibile eseguire il file XML tramite strumenti, ad esempio [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per generare i siti Web di riferimento all'API.

I commenti in formato documentazione XML, come tutti gli altri commenti, vengono ignorati dal compilatore.

È possibile generare il file XML in fase di compilazione eseguendo una delle operazioni seguenti:

- Se si sviluppa un'applicazione con .NET Core dalla riga di comando, è possibile aggiungere un elemento `GenerateDocumentationFile` alla sezione `<PropertyGroup>` del file di progetto con estensione csproj. È anche possibile specificare il percorso del file di documentazione direttamente usando [`DocumentationFile` elemento](/visualstudio/msbuild/common-msbuild-project-properties). L'esempio seguente genera un file XML nella directory del progetto con lo stesso nome file radice dell'assembly:

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```
   
   L'espressione equivale alla seguente:
   
   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- Se si sviluppa un'applicazione tramite Visual Studio, fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**. Nella finestra di dialogo Proprietà selezionare la scheda **Genera** e controllare **File di documentazione XML**. È anche possibile modificare il percorso in cui il compilatore scrive il file.

- Se si compila un'applicazione .NET Framework dalla riga di comando, aggiungere l'opzione del [compilatore-doc](language-reference/compiler-options/doc-compiler-option.md) durante la compilazione.  

I commenti in formato documentazione XML usano tre barre (`///`) e un corpo di commento in formato XML. Ad esempio:

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a>Procedura dettagliata

Esaminiamo la documentazione di una libreria matematica molto semplice per semplificare la comprensione e la collaborazione da parte di nuovi sviluppatori e per gli sviluppatori di terze parti a usare.

Questo è il codice per la semplice libreria matematica:

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

La libreria di esempio supporta quattro operazioni aritmetiche principali, ovvero `add`, `subtract`, `multiply` e `divide` su tipi di dati `int` e `double`.

È ora possibile creare un documento di riferimento per le API dal codice per gli sviluppatori di terze parti che usano la libreria ma non hanno accesso al codice sorgente.
Come accennato in precedenza, è possibile usare tag della documentazione XML a questo scopo. Verranno ora presentati i tag XML standard supportati dal compilatore C#.

## <a name="summary"></a>\<summary>

Il tag `<summary>` aggiunge brevi informazioni su un tipo o membro.
Ne viene illustrato l'uso aggiungendolo alla definizione di classe `Math` e al primo metodo `Add`. È possibile applicarlo al resto del codice.

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

Il tag `<summary>` è molto importante ed è consigliabile includerlo perché il suo contenuto è l'origine principale di informazioni sul tipo o sul membro in IntelliSense o in un documento di riferimento all'API.

## <a name="remarks"></a>\<remarks>

Il tag `<remarks>` integra le informazioni sui tipi o membri definiti dal tag `<summary>`. In questo esempio, sarà sufficiente aggiungerlo alla classe.

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a>\<returns>

Il tag `<returns>` descrive il valore restituito di una dichiarazione di metodo.
Come in precedenza, nell'esempio seguente viene illustrato il tag `<returns>` nel primo metodo `Add`. È possibile eseguire questa operazione su altri metodi.

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a>\<valore>

Il tag `<value>` è simile al tag `<returns>`, ad eccezione del fatto che viene usato per le proprietà.
Se la libreria `Math` avesse una proprietà statica denominata `PI`, questo tag dovrebbe essere usato nel modo seguente:

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a>\<example>

Si usa il tag `<example>` per includere un esempio nella documentazione XML.
Ciò comporta l'uso del tag `<code>` del figlio.

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

Il tag `code` mantiene le interruzioni di riga e il rientro per esempi più lunghi.

## <a name="para"></a>\<para>

Si usa il tag `<para>` per formattare il contenuto all'interno del tag padre. `<para>` viene in genere usato all'interno di un tag, ad esempio `<remarks>` o `<returns>`, per dividere il testo in paragrafi.
È possibile formattare il contenuto del tag `<remarks>` per la definizione delle classi.

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a>\<c>

Nella formattazione si usa il tag `<c>` per contrassegnare parte del testo come codice.
È simile al tag `<code>`, ma è inline. È utile quando si vuole visualizzare un esempio breve di codice come parte del contenuto del tag.
Ora viene aggiornata la documentazione per la classe `Math`.

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a>\<exception>

Tramite il tag `<exception>` è possibile comunicare agli sviluppatori che un metodo può generare eccezioni specifiche.
Esaminando la libreria `Math`, è possibile vedere che entrambi i metodi `Add` generano un'eccezione se viene soddisfatta una determinata condizione. Nonostante non sia così ovvio, anche il metodo `Divide` integer genera eccezioni se il parametro `b` è uguale a zero. Aggiungere ora la documentazione sull'eccezione a questo metodo.

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

L'attributo `cref` rappresenta un riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.
Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento. Il compilatore genererà un avviso se il relativo valore non può essere risolto.

## <a name="see"></a>\<see>

Il tag `<see>` consente di creare un collegamento selezionabile per una pagina di documentazione per un altro elemento di codice. Nel prossimo esempio, verrà creato un collegamento selezionabile tra i due metodi `Add`.

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

L'attributo `cref` è **obbligatorio** e rappresenta un riferimento a un tipo o al suo membro disponibile dall'ambiente di compilazione corrente.
Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.

## <a name="seealso"></a>\<seealso>

Il tag `<seealso>` si usa allo stesso modo del tag `<see>`. L'unica differenza è che il relativo contenuto viene in genere inserito in una sezione "Vedere anche". Di seguito si aggiungerà un tag `seealso` al metodo `Add` integer per fare riferimento ad altri metodi della classe che accettano parametri integer:

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

L'attributo `cref` rappresenta un riferimento a un tipo o al suo membro disponibile dall'ambiente di compilazione corrente.
Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.

## <a name="param"></a>\<param>

Il tag `<param>` viene usato per descrivere i parametri del metodo. Di seguito è riportato un esempio relativo al metodo Double `Add`: il parametro descritto dal tag è specificato nell'attributo `name` **obbligatorio** .

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a>\<typeparam>

Il tag `<typeparam>` viene usato allo stesso modo del tag `<param>`, ma in dichiarazioni di tipo o di metodo generico per descrivere un parametro generico.
Aggiungere un metodo generico semplice alla classe `Math` per verificare se una quantità è maggiore di un'altra.

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a>\<paramref>

A volte è possibile che durante la descrizione dell'operazione di un metodo in un tag `<summary>` si vuole fare un riferimento a un parametro. Il tag `<paramref>` è molto utile per questa operazione. Ora si aggiorna il riepilogo del metodo `Add` basato su double. Analogamente al tag `<param>` il nome del parametro viene specificato nell'attributo `name` **obbligatorio** .

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a>\<typeparamref>

Il tag `<typeparamref>` viene usato allo stesso modo del tag `<paramref>`, ma in dichiarazioni di tipo o di metodo generico per descrivere un parametro generico.
È possibile usare lo stesso metodo generico creato in precedenza.

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a>\<list>

Il tag `<list>` viene usato per formattare le informazioni sulla documentazione come elenco ordinato, elenco non ordinato o tabella.
Creare un elenco non ordinato di ogni operazione matematica supportata dalla libreria `Math`.

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

È possibile creare un elenco ordinato o una tabella sostituendo l'attributo `type` con `number` o `table` rispettivamente.

## <a name="inheritdoc"></a>\<inheritdoc >

È possibile usare il tag `<inheritdoc>` per ereditare i commenti XML da classi base, interfacce e metodi simili. In questo modo si elimina la copia indesiderata e si incollano i commenti XML duplicati e i commenti XML vengono sincronizzati automaticamente.

[!code-csharp-interactive[InheritDoc Tag](~/samples/snippets/csharp/concepts/codedoc/inheritdoc-tag.cs)]

### <a name="put-it-all-together"></a>Riuniamo

Dopo aver eseguito questa esercitazione e applicato i tag al codice, dove necessario, il codice dovrebbe ora essere simile al seguente:

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

Dal codice, è possibile generare un sito Web di documentazione dettagliata completa di riferimenti incrociati. Ciò però potrebbe rendere il codice più difficile da leggere.
In quanto la presenza di un numero elevato di informazioni costituisce un problema molto serio per gli sviluppatori che vogliono contribuire al codice.
Fortunatamente c'è un tag XML che consente di affrontare questo problema:

## <a name="include"></a>\<include>

Il tag `<include>` consente di fare riferimento ai commenti in un file XML separato che descrivono i tipi e i membri nel codice sorgente anziché inserire commenti in formato documentazione direttamente nel file del codice sorgente.

Ora si spostano tutti i tag XML in un file XML separato denominato `docs.xml`. È possibile assegnare al file un nome qualsiasi.

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

Nel codice XML precedente, i commenti in formato documentazione di ogni membro vengono visualizzati direttamente all'interno di un tag denominato dopo le operazioni eseguite. È possibile scegliere una strategia personalizzata.
Ora che i commenti XML si trovano in un file separato, di seguito viene illustrato come il codice può essere reso più leggibile usando il tag `<include>`:

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

Infine si avrà un codice di nuovo leggibile e nessuna informazione sulla documentazione è andata persa.

L'attributo `file` rappresenta il nome del file XML che contiene la documentazione.

L'attributo `path` rappresenta una query [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) nel presente `tag name` del `file` specificato.

L'attributo `name` rappresenta l'identificatore di nome nel tag che precede i commenti.

L'attributo `id` che può essere usato al posto di `name` rappresenta l'ID per il tag che precede i commenti.

### <a name="user-defined-tags"></a>Tag definiti dall'utente

Tutti i tag specificati in precedenza rappresentano i tag riconosciuti dal compilatore C#. Gli utenti comunque possono definire tag personalizzati.
Strumenti come Sandcastle portano il supporto per tag aggiuntivi come [\<> di eventi](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) e [\<nota >](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm)e supportano anche la [documentazione degli spazi dei nomi](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).
Gli strumenti di creazione della documentazione interna o personalizzata possono anche essere usati con i tag standard e con più formati di output da HTML a PDF.

## <a name="recommendations"></a>Suggerimenti

La documentazione del codice è consigliabile per vari motivi. Di seguito vengono illustrate alcune procedure consigliate, scenari di uso generale e altre operazioni che è necessario conoscere quando si usano i tag in formato documentazione XML nel codice C#.

- Per mantenere una certa coerenza, tutti i tipi visibili pubblicamente e i loro membri devono essere documentati. Se necessario, è consigliabile eseguire un'operazione completa.
- I membri private possono anche essere documentati con commenti XML. Ciò espone tuttavia il funzionamento interno della libreria che potrebbe essere riservato.
- Il minimo necessario è che i tipi e i loro membri abbiano i tag `<summary>` perché il loro contenuto è necessario per IntelliSense.
- Il testo della documentazione deve essere scritto usando frasi complete che terminano con un punto.
- Le classi parziali sono completamente supportate e le informazioni sulla documentazione verranno concatenate in una singola voce per tale tipo.
- Il compilatore verifica la sintassi dei tag `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>`e `<typeparam>`.
- Il compilatore convalida i parametri che contengono i percorsi dei file e i riferimenti ad altre parti del codice.

## <a name="see-also"></a>Vedere anche

- [Commenti in formato documentazione XML (Guida per programmatori C#)](programming-guide/xmldoc/index.md)
- [Tag consigliati per i commenti della documentazione (Guida per programmatori C#)](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
