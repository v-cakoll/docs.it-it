---
title: UriTemplate e UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: 106ba21b58dabab96afbc8fb6db5cb305386f2fe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595076"
---
# <a name="uritemplate-and-uritemplatetable"></a>UriTemplate e UriTemplateTable
Gli sviluppatori Web devono poter essere in grado di descrivere la forma e il layout degli URI a cui rispondono i loro servizi. Windows Communication Foundation (WCF) ha aggiunto due nuove classi per consentire agli sviluppatori di controllare gli URI. <xref:System.UriTemplate>e <xref:System.UriTemplateTable> costituiscono la base del motore di invio basato su URI in WCF. Queste classi possono inoltre essere utilizzate autonomamente, consentendo agli sviluppatori di sfruttare i vantaggi dei modelli e del meccanismo di mapping degli URI senza implementare un servizio WCF.  
  
## <a name="templates"></a>Modelli  
 I modelli consentono di descrivere set di URI relativi. Nella tabella seguente il set di modelli URI illustra come definire un sistema per il recupero di vari tipi di informazioni meteorologiche.  
  
|Data|Modello|  
|----------|--------------|  
|Previsioni nazionali|previsioni/nazionali|  
|Previsioni regionali|previsioni/{regione}|  
|Previsioni urbane|previsioni/{regione}/{città}|  
|Previsioni di attività|previsioni/{regione}/{città}/{attività}|  
  
 Questa tabella descrive un insieme di URI simili fra loro dal punto di vista strutturale. Ogni voce è un modello URI. I segmenti nelle parentesi graffe descrivono variabili, mentre quelli non all'interno di parentesi graffe descrivono stringhe letterali. Le classi modello WCF consentono a uno sviluppatore di accettare un URI in ingresso, ad esempio "/Weather/WA/Seattle/Cycling", e di associarlo a un modello che lo descrive, ovvero "/Weather/{state}/{City}/{Activity}".  
  
## <a name="uritemplate"></a>UriTemplate  
 L'elemento <xref:System.UriTemplate> è una classe che incapsula un modello URI. Il costruttore accetta un parametro di stringa che definisce il modello. Questa stringa contiene il modello nel formato descritto nella sezione seguente. La classe <xref:System.UriTemplate> fornisce metodi che consentono di mettere in corrispondenza un URI in ingresso con un modello, generare un URI a partire da un modello, recuperare una raccolta di nomi variabili utilizzati nel modello, determinare se due modelli sono equivalenti e restituire la stringa del modello.  
  
 Il metodo <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> accetta un indirizzo di base e un URI candidato e tenta di creare una corrispondenza tra l'URI e il modello. Se il tentativo ha esito positivo, viene restituita un'istanza della classe <xref:System.UriTemplateMatch>. L'oggetto <xref:System.UriTemplateMatch> contiene un URI di base, l'URI candidato, una raccolta nome/valore dei parametri di query, una matrice di segmenti di percorso relativo, una raccolta nome/valore di variabili di cui era stata creata una corrispondenza, l'istanza <xref:System.UriTemplate> utilizzata per creare la corrispondenza, una stringa contenente eventuali porzioni prive di corrispondenza dell'URI candidato (utilizzate se il modello contiene un carattere jolly) e un oggetto associato al modello.  
  
> [!NOTE]
> Quando viene creata una corrispondenza tra un URI candidato e un modello, la classe <xref:System.UriTemplate> ignora lo schema e il numero di porta.  
  
 Sono disponibili due metodi che consentono di generare un URI da un modello: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> e <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>. Il metodo <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> accetta un indirizzo di base e una raccolta nome/valore di parametri. Questi parametri vengono sostituiti con le variabili quando il modello viene associato. Il metodo <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> accetta invece le coppie nome/valore e le sostituisce da sinistra a destra.  
  
 Il metodo <xref:System.UriTemplate.ToString> restituisce la stringa di modello.  
  
 La proprietà <xref:System.UriTemplate.PathSegmentVariableNames%2A> contiene la raccolta dei nomi delle variabili utilizzate all'interno dei segmenti di percorso contenuti nella stringa di modello.  
  
 Il metodo <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> accetta un oggetto <xref:System.UriTemplate> come parametro e restituisce un valore booleano che specifica se i due modelli sono equivalenti. Per ulteriori informazioni, vedere la sezione relativa all'equivalenza dei modelli più avanti in questo argomento.  
  
 <xref:System.UriTemplate> può essere utilizzato con qualsiasi schema URI conforme alla grammatica URI HTTP. Di seguito vengono riportati esempi di schemi URI supportati.  
  
- `http://`  
  
- `https://`  
  
- `net.tcp://`  
  
- `net.pipe://`  
  
- `sb://`  
  
 Schemi come file:// e urn:// non sono conformi alla grammatica URI HTTP e causeranno risultati imprevisti se utilizzati con modelli URI.  
  
### <a name="template-string-syntax"></a>Sintassi della stringa di modello  
 Ogni modello presenta tre parti: un percorso, una query facoltativa e un frammento facoltativo. Si consideri ad esempio il modello seguente:  
  
`"/weather/{state}/{city}?forecast={length)#frag1`  
  
 Il percorso è "/previsioni/{regione}/{città}", la query è "?previsioni={durata)" e il frammento è "#framm1".  
  
 Le barre iniziali e finali sono facoltative nell'espressione del percorso. Le espressioni di query e di frammento possono essere omesse del tutto. Un percorso è costituito da una serie di segmenti delimitati da'/', ogni segmento può avere un valore letterale, un nome di variabile (scritto in {parentesi graffe}) o un carattere jolly (scritto come ' \* '). Nel modello precedente il segmento "\previsioni\ è un valore letterale, mentre"{regione}" e "{città}" rappresentano variabili. Le variabili prendono il nome dal contenuto delle parentesi graffe e possono essere sostituite in un secondo momento con un valore concreto per creare un *URI chiuso*. Il carattere jolly è facoltativo, ma può essere visualizzato solo alla fine dell'URI, dove corrisponde logicamente al resto del percorso.  
  
 L'espressione di query, se presente, specifica una serie di coppie nome/valore non ordinate delimitate da "&". Gli elementi dell'espressione di query possono essere coppie letterali (x=2) o una coppia variabile (x={var}). Solo il lato destro della query può contenere un'espressione variabile. ({someName} = {someValue} non è consentito. Non è consentito utilizzare valori non abbinati (?x). Non c'è differenza tra un'espressione di query vuota e un'espressione di query contenente il solo carattere "?". Entrambe significano infatti "qualsiasi query".  
  
 L'espressione di frammento può essere data da un valore letterale. Non sono consentite le variabili.  
  
 Tutti i nomi variabili del modello contenuti in una stringa di modello devono essere univoci. I nomi variabili del modello non fanno distinzione tra maiuscole e minuscole.  
  
 Esempi di stringhe di modello valide:  
  
- ""  
  
- "/casa"  
  
- "/Shoe/ \* "  
  
- "{casa}/stanza"  
  
- "{Shoe}/{Boat}/Bed/{quilt}"  
  
- "scarpa/{Boat}"  
  
- "scarpa/{Boat}/ \* "  
  
- "scarpa/barca? x = 2"  
  
- "scarpa/{Boat}? x = {letto}"  
  
- "scarpa/{Boat}? x = {Bed} &y = band"  
  
- "? x = {Shoe}"  
  
- "scarpa? x = 3&y = {var}  
  
 Esempi di stringhe di modello non valide:  
  
- "{Shoe}/{SHOE}/x = 2": nomi di variabili duplicati.  
  
- "{Shoe}/Boat/? Bed = {Shoe}": nomi di variabili duplicati.  
  
- "? x = 2&x = 3": le coppie nome/valore all'interno di una stringa di query devono essere univoche, anche se sono valori letterali.  
  
- "? x = 2&": il formato della stringa di query non è valido.  
  
- "? 2&x = {Shoe}": la stringa di query deve essere costituita da coppie nome/valore.  
  
- "? y = 2&&X = 3": la stringa di query deve essere costituita da coppie nome-valore. i nomi non possono iniziare con ' &'.  
  
### <a name="compound-path-segments"></a>Segmenti di percorso composti  
 I segmenti di percorso composti consentono a un singolo segmento di percorso URI di contenere più variabili, nonché variabili combinate con valori letterali. Di seguito vengono riportati esempi di segmenti di percorso composti validi.  
  
- /nomefile.{ext}/  
  
- /{nomefile}.jpg/  
  
- /{nomefile}.{ext}/  
  
- /{a}.{b}someLiteral{c}({d})/  
  
 Di seguito vengono riportati esempi di segmenti di percorso non validi.  
  
- Le {} variabili/-devono essere denominate.  
  
- /{casa}{stanza}: le variabili devono essere separate da un valore letterale.  
  
### <a name="matching-and-compound-path-segments"></a>Segmenti di percorso composti e corrispondenti  
 I segmenti di percorso composti consentono di definire un UriTemplate che dispone di più variabili all'interno di un solo segmento di percorso. Ad esempio, nella stringa di modello seguente: "Addresss/{state}. {City} "due variabili (stato e città) vengono definite all'interno dello stesso segmento. Questo modello corrisponderebbe a un URL come, `http://example.com/Washington.Redmond` ma corrisponderà anche a un URL come `http://example.com/Washington.Redmond.Microsoft` . Nel secondo caso, la variabile di stato conterrà "Washington" e la variabile City conterrà "Redmond. Microsoft". In questo caso il qualsiasi testo (eccetto '/') corrisponderà alla variabile {city}. Se si desidera un modello che non corrisponderà al testo "extra", inserire la variabile in un segmento di modello separato, ad esempio: "Addresss/{state}/{City}.  
  
### <a name="named-wildcard-segments"></a>Segmenti con caratteri jolly con nome  
 Un segmento con carattere jolly denominato è qualsiasi segmento di variabile di percorso il cui nome di variabile inizia con il carattere jolly " \* ". La stringa di modello seguente contiene un segmento con carattere jolly con nome denominato "casa".  
  
`"literal/{*shoe}"`  
  
 I segmenti con caratteri jolly devono rispettare le regole seguenti:  
  
- Per ogni stringa di modello può esistere al massimo un segmento con carattere jolly con nome.  
  
- Un segmento con carattere jolly con nome deve comparire nel segmento all'estrema destra del percorso.  
  
- Un segmento con carattere jolly con nome non può coesistere con un segmento con carattere jolly anonimo all'interno della stessa stringa di modello.  
  
- Il nome di un segmento con carattere jolly con nome deve essere univoco.  
  
- I segmenti con carattere jolly con nome non possono disporre di valori predefiniti.  
  
- I segmenti con carattere jolly con nome non possono terminare con "/".  
  
### <a name="default-variable-values"></a>Valori di variabili predefiniti  
 I valori di variabili predefiniti consentono di specificare valori predefiniti per variabili all'interno di un modello. È possibile specificare le variabili predefinite con parentesi graffe che dichiarano la variabile o come una raccolta passata al costruttore UriTemplate. Nel modello seguente vengono illustrati due modi per specificare <xref:System.UriTemplate> con variabili con valori predefiniti.  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 Questo modello dichiara una variabile denominata `a` con valore predefinito `1` e una variabile denominata `b` con valore predefinito `5`.  
  
> [!NOTE]
> Solo le variabili del segmento di percorso possono presentare valori predefiniti. Le variabili delle stringhe di query, dei segmenti composti e quelle con carattere jolly con nome non possono presentare valori predefiniti.  
  
 Nell'esempio di codice seguente viene illustrato come gestire i valori di variabili predefiniti quando si crea una corrispondenza con un URI candidato.  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");

UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);
Uri candidate = new Uri("http://localhost:8000/OR");

UriTemplateMatch m1 = t.Match(baseAddress, candidate);

Console.WriteLine($"Template: {t}");
Console.WriteLine($"Candidate URI: {candidate}");

// Display contents of BoundVariables
Console.WriteLine("BoundVariables:");
foreach (string key in m1.BoundVariables.AllKeys)
{
    Console.WriteLine($"\t{key}={m1.BoundVariables[key]}");
}
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/
// Candidate URI: http://localhost:8000/OR
// BoundVariables:
//         STATE=OR
//         CITY=Redmond
```  
  
> [!NOTE]
> Un URI, ad esempio `http://localhost:8000///` , non corrisponde al modello elencato nel codice precedente, tuttavia è un URI come `http://localhost:8000/` .  
  
 Nell'esempio di codice seguente viene illustrato come gestire i valori di variabili predefiniti quando si crea un URI con un modello.  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
Quando a una variabile viene assegnato il valore predefinito `null`, è necessario tenere conto di alcuni vincoli aggiuntivi. Una variabile può presentare il valore predefinito `null` se è contenuta nel segmento più a destra della stringa del modello o se tutti i segmenti a destra del segmento presentano valori predefiniti `null`. Di seguito vengono riportate stringhe di modello valide con valori predefiniti `null`:  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 Di seguito sono riportate stringhe di modello non valide con valori predefiniti `null` :  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a>Valori predefiniti e corrispondenza  
 Quando si crea una corrispondenza tra un URI candidato e un modello con valori predefiniti, se i valori non sono specificati nell'URI candidato i valori predefiniti verranno inseriti nella raccolta <xref:System.UriTemplateMatch.BoundVariables%2A>.  
  
### <a name="template-equivalence"></a>Equivalenza fra modelli  
 Due modelli sono definiti *strutturalmente equivalenti* quando tutti i valori letterali dei modelli corrispondono e hanno variabili negli stessi segmenti. Ad esempio, i modelli seguenti sono strutturalmente equivalenti:  
  
- /a/{var1}/b b/{var2}? x = 1&y = 2  
  
- a/{x}/b% 20B/{var1}? y = 2&x = 1  
  
- a/{y}/B% 20B/{z}/? y = 2&x = 1  
  
 Alcune considerazioni:  
  
- Se un modello contiene barre iniziali, solo la prima viene ignorata.  
  
- Quando si verifica se due stringhe di modello sono strutturalmente equivalenti, i nomi variabili, i segmenti di percorso e le stringhe di query non fanno distinzione fra maiuscole e minuscole.  
  
- Le stringhe di query non sono ordinate.  
  
## <a name="uritemplatetable"></a>UriTemplateTable  
 La classe <xref:System.UriTemplateTable> rappresenta una tabella associativa di oggetti <xref:System.UriTemplate> associata a un oggetto scelto dallo sviluppatore. Ogni tabella <xref:System.UriTemplateTable> deve contenere almeno un modello <xref:System.UriTemplate> prima di chiamare il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>. È possibile modificare il contenuto di <xref:System.UriTemplateTable> finché non viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>. Quando viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> viene eseguita una convalida il cui tipo dipende dal valore del parametro `allowMultiple` da passare al metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.  
  
 Quando al metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> viene passato il valore `false`, l'oggetto <xref:System.UriTemplateTable> verifica se la tabella contiene modelli. Se rileva modelli strutturalmente equivalenti, genera un'eccezione. Questo metodo viene utilizzato insieme al metodo <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> quando si desidera garantire che solo un modello corrisponda a un determinato URI in ingresso.  
  
 Quando viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> passando `true`, <xref:System.UriTemplateTable> consente la presenza di più modelli strutturalmente equivalenti all'interno di <xref:System.UriTemplateTable>.  
  
 Se un set di oggetti <xref:System.UriTemplate> aggiunti a un oggetto <xref:System.UriTemplateTable> contiene stringhe di query, queste non devono essere ambigue. È tuttavia consentito utilizzare stringhe di query identiche.  
  
> [!NOTE]
> Mentre <xref:System.UriTemplateTable> consente la presenza di indirizzi di base che utilizzano schemi diversi da HTTP, lo schema e il numero di porta vengono ignorati quando si creano corrispondenze tra URI candidati e modelli.  
  
### <a name="query-string-ambiguity"></a>Ambiguità delle stringhe di query  
 I modelli che condividono un percorso equivalente contengono stringhe di query ambigue se esiste un URI che corrisponde a più di un modello.  
  
 I set seguenti di stringhe di query non sono ambigui fra loro:  
  
- ?x=1  
  
- ?x=2  
  
- ?x=3  
  
- ? x = 1&y = {var}  
  
- ? x = 2&z = {var}  
  
- ?x=3  
  
- ?x=1  
  
- ?  
  
- ? x={var}  
  
- ?  
  
- ? m = Get&c = RSS  
  
- ? m = put&c = RSS  
  
- ? m = Get&c = Atom  
  
- ? m = put&c = Atom  
  
 I set seguenti di modelli di stringhe di query sono ambigui fra loro:  
  
- ?x=1  
  
- ?x={var}  
  
 "x=1": corrisponde a entrambi i modelli.  
  
- ?x=1  
  
- ?y=2  
  
 "x = 1&y = 2" corrisponde a entrambi i modelli. Ciò è dovuto al fatto che una stringa di query può contenere più variabili di stringa rispetto al modello a cui corrisponde.  
  
- ?x=1  
  
- ? x = 1&y = {var}  
  
 "x = 1&y = 3" corrisponde a entrambi i modelli.  
  
- ? x = 3&y = 4  
  
- ? x = 3&z = 5  
  
> [!NOTE]
> I caratteri á e Á sono considerati caratteri diversi quando vengono visualizzati come parte di un percorso URI o di un <xref:System.UriTemplate> valore letterale del segmento di percorso (ma i caratteri a e a sono considerati uguali). I caratteri á e Á sono considerati gli stessi caratteri quando vengono visualizzati come parte di un <xref:System.UriTemplate> {variablename} o una stringa di query (e un oggetto e un oggetto sono considerati anche gli stessi caratteri).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul modello di programmazione HTTP Web WCF](wcf-web-http-programming-model-overview.md)
- [Modello a oggetti per la programmazione HTTP Web di WCF](wcf-web-http-programming-object-model.md)
- [UriTemplate](../samples/uritemplate-sample.md)
- [Tabella UriTemplate](../samples/uritemplate-table-sample.md)
- [Dispatcher della tabella UriTemplate](../samples/uritemplate-table-dispatcher-sample.md)
