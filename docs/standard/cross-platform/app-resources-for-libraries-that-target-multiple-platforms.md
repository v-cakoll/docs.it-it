---
title: Risorse app per librerie destinate a più piattaforme
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multiple platforms, resources for
- resources [.NET Framework]
- .NET Framework, resources when targeting multiple platforms
- resources, for multiple platforms
- targeting multiple platforms, resources for
ms.assetid: 72c76f0b-7255-4576-9261-3587f949669c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e846f45b55ac09d6ce6af4f3223c3bdba1dc83ba
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506007"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Risorse app per librerie destinate a più piattaforme
È possibile usare .NET Framework [libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) tipo per garantire che le risorse nelle librerie di classi sono accessibili da più piattaforme progetto. Questo tipo di progetto è disponibile in Visual Studio 2012 e fa riferimento al subset portabile della libreria di classi .NET Framework. Utilizzo di una libreria di classi portabile assicura che la libreria è possibile accedere da app desktop, applicazioni Silverlight, le app di Windows Phone, e [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 Il progetto libreria di classi portabile effettua solo un subset molto limitato dei tipi nel <xref:System.Resources> dello spazio dei nomi disponibile per l'applicazione, ma sarà possibile usare il <xref:System.Resources.ResourceManager> classe da cui recuperare le risorse. Tuttavia, se si crea un'applicazione tramite Visual Studio, è necessario usare il wrapper fortemente tipizzato creato da Visual Studio anziché usare la classe <xref:System.Resources.ResourceManager> direttamente.

 Per creare un wrapper fortemente tipizzato in Visual Studio, impostare il file di risorse principale **modificatore di accesso** in Progettazione risorse di Visual Studio per **pubblico**. Ciò crea un file [resourceFileName].designer.cs o [resourceFileName].designer.vb che contiene il wrapper ResourceManager fortemente tipizzato. Per altre informazioni sull'uso di un wrapper di risorse fortemente tipizzata, vedere la sezione "Generazione di una classe fortemente tipizzata risorsa" nel [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) argomento.

## <a name="resource-manager-in-the-portable-class-library"></a>Resource Manager nella libreria di classi portabile
 In un progetto libreria di classi portabile, tutti gli accessi alle risorse viene gestito dal <xref:System.Resources.ResourceManager> classe. Poiché tipi nel <xref:System.Resources> dello spazio dei nomi, come <xref:System.Resources.ResourceReader> e <xref:System.Resources.ResourceSet>, sono non è accessibile da un progetto libreria di classi portabile, non possono essere usati per accedere alle risorse.

 Il progetto libreria di classi portabile include i quattro <xref:System.Resources.ResourceManager> i membri elencati nella tabella seguente. Questi costruttori e metodi consentono di creare un'istanza di un oggetto <xref:System.Resources.ResourceManager> e recuperare le risorse di tipo stringa.

|Membro`ResourceManager`|Descrizione|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Crea un'istanza di <xref:System.Resources.ResourceManager> per accedere al file di risorse denominato individuato nell'assembly specificato.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Crea un'istanza di <xref:System.Resources.ResourceManager> che corrisponde al tipo specificato.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Recupera una risorsa denominata per impostazioni cultura specifiche.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Recupera una risorse denominata per impostazioni cultura specifiche.|

 L'esclusione di altri <xref:System.Resources.ResourceManager> non è possibile recuperare i membri da significa che la libreria di classi portabile che serializzati oggetti, dati non di tipo stringa e immagini da un file di risorse. Per utilizzare le risorse da una libreria di classi portabile, è consigliabile archiviare tutti i dati oggetto in formato stringa. Ad esempio, è possibile archiviare valori numerici in un file di risorse convertendoli in stringhe e recuperarli per poi riconvertirli in numeri usando il metodo `Parse` o `TryParse` del tipo di dati numerico. È possibile convertire immagini o altri dati binari in una rappresentazione di stringa chiamando il metodo <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> e ripristinarli in una matrice di byte chiamando il metodo <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>La libreria di classi portabile e le app di Windows Store
 Progetti libreria di classi portabile archiviano le risorse in file con estensione resx, che vengono quindi compilati in file. Resources e incorporati nell'assembly principale o in assembly satellite in fase di compilazione. Le applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], invece, richiedono che le risorse vengano archiviate nei file .resw, che vengono compilati in un singolo file di indice risorse (PRI). Tuttavia, nonostante i formati di file non compatibile, la libreria di classi portabile funzionerà un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.

 Per utilizzare la libreria di classi da un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], aggiungere un riferimento al progetto di applicazione Windows Store. Visual Studio in modo trasparente estrarre le risorse dall'assembly in un file. resw e verrà utilizzato per generare un file PRI da cui il Runtime di Windows può estrarre le risorse. In fase di esecuzione, il Runtime di Windows esegue il codice della libreria di classi portabile, ma recupera le risorse della libreria di classi di portabile dal file PRI.

 Se il progetto libreria di classi portabile contiene risorse localizzate, utilizzare il modello hub e spoke per distribuirle proprio come si farebbe per una libreria in un'app desktop. Per usare il file di risorse principale e qualunque file di risorse localizzate in un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], aggiungere un riferimento all'assembly originale. In fase di compilazione, Visual Studio estrae le risorse dal file di risorse principale ed ogni file di risorse localizzate in file .resw separati. Quindi, viene compilato i file. resw in un unico file PRI che il Runtime di Windows accede in fase di esecuzione.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Esempio: Libreria di classi portabile non localizzato
 L'esempio di libreria di classi portabile semplice e non localizzato seguente usa le risorse per archiviare i nomi delle colonne e per determinare il numero di caratteri da riservare per i dati tabulari. Nell'esempio viene utilizzato un file denominato LibResources.resx per archiviare le risorse di tipo stringa elencate nella tabella seguente.

|Nome della risorsa|Valore della risorsa|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|Data assunzione|
|HiredLength|12|
|Id|Id|
|ID.Length|12|
|Nome|Nome|
|NameLength|25|
|Titolo|Employee Database|

 Il codice seguente definisce una `UILibrary` classe che utilizza il wrapper di Resource Manager denominato `resources` generato da Visual Studio quando il **modificatore di accesso** per il file viene modificato in **pubblica** . La classe UILibrary analizza i dati della stringa, se necessario. . Notare che la classe si trova nello spazio dei nomi `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 Nell'esempio di codice riportato di seguito viene illustrato come sia possibile accedere alla classe `UILibrary` e alle relative risorse da una applicazione in modalità console. Richiede un riferimento a Uilibrary da aggiungere al progetto di app console.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 Il codice seguente mostra come sia possibile accedere alla classe `UILibrary` e alle relative risorse da un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Richiede un riferimento a Uilibrary da aggiungere al progetto di app Windows Store.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Esempio: Libreria di classi portabile localizzato
 L'esempio di libreria di classi portabile localizzato seguente include le risorse per le impostazioni cultura inglese (Stati Uniti) e il francese (Francia). Le impostazioni cultura inglese (Stati Uniti) rappresenta impostazioni cultura predefinite dell'app; le risorse vengono illustrate nella tabella di [sezione precedente](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Il file di risorse per le impostazioni cultura francesi (Francia) è denominato LibResources.fr-FR.resx ed è costituito dalle risorse di tipo stringa elencate nella tabella seguente. Il codice sorgente per la classe `UILibrary` è lo stesso di quello riportato nella sezione precedente.

|Nome della risorsa|Valore della risorsa|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|Id|Id|
|Nome|Nom|
|Titolo|Base de données des employés|

 Nell'esempio di codice riportato di seguito viene illustrato come sia possibile accedere alla classe `UILibrary` e alle relative risorse da una applicazione in modalità console. Richiede un riferimento a Uilibrary da aggiungere al progetto di app console.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 Il codice seguente mostra come sia possibile accedere alla classe `UILibrary` e alle relative risorse da un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Richiede un riferimento a Uilibrary da aggiungere al progetto di app Windows Store. Usa la proprietà statica `ApplicationLanguages.PrimaryLanguageOverride` per impostare la lingua preferita dell'applicazione in francese.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Resources.ResourceManager>
- [Risorse nelle applicazioni desktop](../../../docs/framework/resources/index.md)
- [Creazione del pacchetto e distribuzione delle risorse](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
