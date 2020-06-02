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
ms.openlocfilehash: a2d02a8ebe5e2611db3bc284bb022470ff77f601
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290357"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Risorse app per librerie destinate a più piattaforme
È possibile utilizzare il tipo di progetto [libreria di classi](cross-platform-development-with-the-portable-class-library.md) portabile .NET Framework per assicurarsi che le risorse nelle librerie di classi siano accessibili da più piattaforme. Questo tipo di progetto è disponibile in Visual Studio 2012 e è destinato al subset portabile della libreria di classi .NET Framework. L'uso di una libreria di classi portabile garantisce che sia possibile accedere alla libreria da applicazioni desktop, applicazioni Silverlight, Windows Phone app e app di Windows 8. x Store.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 Il progetto libreria di classi portabile rende disponibile all'applicazione solo un subset molto limitato dei tipi nello <xref:System.Resources> spazio dei nomi, ma consente di utilizzare la <xref:System.Resources.ResourceManager> classe per recuperare le risorse. Tuttavia, se si crea un'applicazione tramite Visual Studio, è necessario usare il wrapper fortemente tipizzato creato da Visual Studio anziché usare la classe <xref:System.Resources.ResourceManager> direttamente.

 Per creare un wrapper fortemente tipizzato in Visual Studio, impostare il **modificatore di accesso** del file di risorse principale in Progettazione risorse di Visual Studio su **public**. Ciò crea un file [resourceFileName].designer.cs o [resourceFileName].designer.vb che contiene il wrapper ResourceManager fortemente tipizzato. Per ulteriori informazioni sull'utilizzo di un wrapper di risorse fortemente tipizzato, vedere la sezione "generazione di una classe di risorse fortemente tipizzata" nell'argomento [Resgen. exe (Generatore di file di risorse)](../../framework/tools/resgen-exe-resource-file-generator.md) .

## <a name="resource-manager-in-the-portable-class-library"></a>Gestione risorse nella libreria di classi portabile
 In un progetto libreria di classi portabile, tutti gli accessi alle risorse vengono gestiti dalla <xref:System.Resources.ResourceManager> classe. Poiché i tipi nello <xref:System.Resources> spazio dei nomi, ad esempio <xref:System.Resources.ResourceReader> e <xref:System.Resources.ResourceSet> , non sono accessibili da un progetto libreria di classi portabile, non possono essere usati per accedere alle risorse.

 Il progetto libreria di classi portabile include i quattro <xref:System.Resources.ResourceManager> membri elencati nella tabella seguente. Questi costruttori e metodi consentono di creare un'istanza di un oggetto <xref:System.Resources.ResourceManager> e recuperare le risorse di tipo stringa.

|Membro`ResourceManager`|Descrizione|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Crea un'istanza di <xref:System.Resources.ResourceManager> per accedere al file di risorse denominato individuato nell'assembly specificato.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Crea un'istanza di <xref:System.Resources.ResourceManager> che corrisponde al tipo specificato.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Recupera una risorsa denominata per impostazioni cultura specifiche.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Recupera una risorse denominata per impostazioni cultura specifiche.|

 L'esclusione di altri <xref:System.Resources.ResourceManager> membri dalla libreria di classi portabile significa che gli oggetti serializzati, i dati non di tipo stringa e le immagini non possono essere recuperati da un file di risorse. Per usare le risorse di una libreria di classi portabile, è necessario archiviare tutti i dati oggetto in formato stringa. Ad esempio, è possibile archiviare valori numerici in un file di risorse convertendoli in stringhe e recuperarli per poi riconvertirli in numeri usando il metodo `Parse` o `TryParse` del tipo di dati numerico. È possibile convertire immagini o altri dati binari in una rappresentazione di stringa chiamando il metodo <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> e ripristinarli in una matrice di byte chiamando il metodo <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>Libreria di classi portabile e app di Windows Store
 I progetti libreria di classi portabile archiviano le risorse nei file con estensione resx, che vengono quindi compilati in file con estensione resources e incorporati nell'assembly principale o in assembly satellite in fase di compilazione. Le app di Windows 8. x Store, d'altra parte, richiedono l'archiviazione delle risorse nei file con estensione resw, che vengono quindi compilate in un unico file di indice delle risorse del pacchetto (PRI). Tuttavia, nonostante i formati di file non compatibili, la libreria di classi portabile funzionerà in un'app di Windows 8. x Store.

 Per utilizzare la libreria di classi da un'app di Windows 8. x Store, aggiungere un riferimento ad esso nel progetto di app di Windows Store. Visual Studio estrae in modo trasparente le risorse dall'assembly in un file con estensione resw e le usa per generare un file PRI da cui il Windows Runtime può estrarre le risorse. In fase di esecuzione, il Windows Runtime esegue il codice nella libreria di classi portabile, ma recupera le risorse della libreria di classi portabile dal file PRI.

 Se il progetto libreria di classi portabile include risorse localizzate, usare il modello hub e spoke per distribuirle esattamente come per una libreria in un'app desktop. Per utilizzare il file di risorse principale e tutti i file di risorse localizzati nell'app di Windows 8. x Store, è necessario aggiungere un riferimento all'assembly principale. In fase di compilazione, Visual Studio estrae le risorse dal file di risorse principale ed ogni file di risorse localizzate in file .resw separati. Compila quindi i file con estensione resw in un unico file PRI a cui il Windows Runtime accede in fase di esecuzione.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Esempio: libreria di classi portabile non localizzata
 Nell'esempio di libreria di classi portabile non localizzato seguente vengono utilizzate risorse per archiviare i nomi delle colonne e per determinare il numero di caratteri da riservare per i dati tabulari. Nell'esempio viene utilizzato un file denominato LibResources.resx per archiviare le risorse di tipo stringa elencate nella tabella seguente.

|Nome risorsa|Valore della risorsa|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|Data assunzione|
|HiredLength|12|
|ID|ID|
|ID.Length|12|
|Nome|Nome|
|NameLength|25|
|Titolo|Employee Database|

 Il codice seguente definisce una `UILibrary` classe che usa il wrapper gestione risorse denominato `resources` generato da Visual Studio quando il **modificatore di accesso** per il file viene modificato in **public**. La classe UILibrary analizza i dati della stringa, se necessario. . Notare che la classe si trova nello spazio dei nomi `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 Nell'esempio di codice riportato di seguito viene illustrato come sia possibile accedere alla classe `UILibrary` e alle relative risorse da una applicazione in modalità console. Richiede l'aggiunta di un riferimento a UILibrary. dll al progetto di applicazione console.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 Il codice seguente illustra il modo `UILibrary` in cui è possibile accedere alla classe e alle relative risorse da un'app di Windows 8. x Store. Richiede l'aggiunta di un riferimento a UILibrary. dll al progetto di app di Windows Store.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Esempio: libreria di classi portabile localizzata
 Il seguente esempio di libreria di classi portabile localizzata include risorse per le impostazioni cultura francese (Francia) e inglese (Stati Uniti). Le impostazioni cultura della lingua inglese (Stati Uniti) sono le impostazioni cultura predefinite dell'app; le relative risorse vengono visualizzate nella tabella della [sezione precedente](app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Il file di risorse per le impostazioni cultura francesi (Francia) è denominato LibResources.fr-FR.resx ed è costituito dalle risorse di tipo stringa elencate nella tabella seguente. Il codice sorgente per la classe `UILibrary` è lo stesso di quello riportato nella sezione precedente.

|Nome risorsa|Valore della risorsa|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|ID|ID|
|Nome|Nom|
|Titolo|Base de données des employés|

 Nell'esempio di codice riportato di seguito viene illustrato come sia possibile accedere alla classe `UILibrary` e alle relative risorse da una applicazione in modalità console. Richiede l'aggiunta di un riferimento a UILibrary. dll al progetto di applicazione console.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 Il codice seguente illustra il modo `UILibrary` in cui è possibile accedere alla classe e alle relative risorse da un'app di Windows 8. x Store. Richiede l'aggiunta di un riferimento a UILibrary. dll al progetto di app di Windows Store. Usa la proprietà statica `ApplicationLanguages.PrimaryLanguageOverride` per impostare la lingua preferita dell'applicazione in francese.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Resources.ResourceManager>
- [Risorse nelle applicazioni desktop](../../framework/resources/index.md)
- [Packaging and Deploying Resources](../../framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
