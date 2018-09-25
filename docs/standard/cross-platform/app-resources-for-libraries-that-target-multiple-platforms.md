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
ms.openlocfilehash: a6c589a393ccfb5610a19776af6e33e4046bf5d3
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711311"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Risorse app per librerie destinate a più piattaforme
È possibile usare .NET Framework [libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) tipo per garantire che le risorse nelle librerie di classi sono accessibili da più piattaforme progetto. Il tipo di progetto è disponibile in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] e fa riferimento al subset portabile della libreria di classi di .NET Framework. Usando la [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] viene garantito che sia possibile accedere alla libreria da applicazioni desktop, applicazioni Silverlight, applicazioni Windows Phone e da applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]
  
 Il progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] crea solo un subset molto limitato dei tipi nello spazio dei nomi di <xref:System.Resources> disponibile per l'applicazione, ma consente di usare la classe <xref:System.Resources.ResourceManager> per recuperare le risorse. Tuttavia, se si crea un'applicazione tramite Visual Studio, è necessario usare il wrapper fortemente tipizzato creato da Visual Studio anziché usare la classe <xref:System.Resources.ResourceManager> direttamente.  
  
 Per creare un wrapper fortemente tipizzato in Visual Studio, impostare il file di risorse principale **modificatore di accesso** in Progettazione risorse di Visual Studio per **pubblico**. Ciò crea un file [resourceFileName].designer.cs o [resourceFileName].designer.vb che contiene il wrapper ResourceManager fortemente tipizzato. Per altre informazioni sull'uso di un wrapper di risorse fortemente tipizzata, vedere la sezione "Generazione di una classe fortemente tipizzata risorsa" nel [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) argomento.  
  
## <a name="resource-manager-in-the-includenetportableincludesnet-portable-mdmd"></a>Gestione risorse in [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 In un progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], tutti gli accessi alle risorse sono gestiti dalla classe <xref:System.Resources.ResourceManager>. Poiché i tipi nello spazio dei nomi <xref:System.Resources>, come <xref:System.Resources.ResourceReader> e <xref:System.Resources.ResourceSet>, non sono accessibili da un progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], non possono essere usati per accedere alle risorse.  
  
 Il progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] include i quattro membri <xref:System.Resources.ResourceManager> elencati nella tabella seguente. Questi costruttori e metodi consentono di creare un'istanza di un oggetto <xref:System.Resources.ResourceManager> e recuperare le risorse di tipo stringa.  
  
|Membro `ResourceManager`|Descrizione|  
|------------------------------|-----------------|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Crea un'istanza di <xref:System.Resources.ResourceManager> per accedere al file di risorse denominato individuato nell'assembly specificato.|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Crea un'istanza di <xref:System.Resources.ResourceManager> che corrisponde al tipo specificato.|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Recupera una risorsa denominata per impostazioni cultura specifiche.|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Recupera una risorse denominata per impostazioni cultura specifiche.|  
  
 L'esclusione di altri membri <xref:System.Resources.ResourceManager> da [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] significa che oggetti serializzati, dati non di tipo stringa e immagini non possono essere recuperati da un file di risorse. Per usare le risorse da [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], è necessario memorizzare tutti i dati oggetto in forma di stringa. Ad esempio, è possibile archiviare valori numerici in un file di risorse convertendoli in stringhe e recuperarli per poi riconvertirli in numeri usando il metodo `Parse` o `TryParse` del tipo di dati numerico. È possibile convertire immagini o altri dati binari in una rappresentazione di stringa chiamando il metodo <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> e ripristinarli in una matrice di byte chiamando il metodo <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.  
  
## <a name="the-includenetportableincludesnet-portable-mdmd-and-windows-store-apps"></a>[!INCLUDE[net_portable](../../../includes/net-portable-md.md)] e applicazioni Windows Store  
 I progetti [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] archiviano le risorse in file .resx, che vengono quindi compilati in file .resources e incorporati nell'assembly principale o in assembly satellite in fase di compilazione. Le applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], invece, richiedono che le risorse vengano archiviate nei file .resw, che vengono compilati in un singolo file di indice risorse (PRI). Tuttavia, nonostante l'incompatibilità dei formati dei file, la [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] funzionerà in un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
 Per usare la libreria di classi da un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], aggiungere un riferimento al progetto di applicazione Windows Store. Visual Studio estrarrà in modo trasparente le risorse dall'assembly in un file .resw e le userà per generare un file PRI da cui [!INCLUDE[wrt](../../../includes/wrt-md.md)] potranno essere estratte le risorse. In fase di esecuzione, [!INCLUDE[wrt](../../../includes/wrt-md.md)] esegue il codice nella [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], ma recupera le risorse della Libreria di classi portabile dal file PRI.  
  
 Se il progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] include risorse localizzate, usare il modello hub and spoke per distribuirle proprio come avviene per una libreria in un'applicazione desktop. Per usare il file di risorse principale e qualunque file di risorse localizzate in un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], aggiungere un riferimento all'assembly originale. In fase di compilazione, Visual Studio estrae le risorse dal file di risorse principale ed ogni file di risorse localizzate in file .resw separati. Vengono quindi compilate i file .resw in un singolo file PRI a cui [!INCLUDE[wrt](../../../includes/wrt-md.md)] accede in fase di esecuzione.  
  
<a name="NonLoc"></a>   
## <a name="example-non-localized-includenetportableincludesnet-portable-mdmd"></a>Esempio: [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] non localizzata  
 Il seguente semplice esempio di [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] non localizzata usa le risorse per archiviare i nomi delle colonne e per determinare il numero di caratteri da riservare ai dati tabulari. Nell'esempio viene usato un file denominato LibResources.resx per archiviare le risorse di tipo stringa elencate nella tabella seguente.  
  
|Nome della risorsa|Valore della risorsa|  
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
  
 Il codice seguente definisce una `UILibrary` classe che utilizza il wrapper di Resource Manager denominato `resources` generato da Visual Studio quando il **modificatore di accesso** per il file viene modificato in **pubblica** . La classe UILibrary analizza i dati della stringa, se necessario. . Notare che la classe si trova nello spazio dei nomi `MyCompany.Employees`.  
  
 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]  
  
 Nell'esempio di codice riportato di seguito viene illustrato come sia possibile accedere alla classe `UILibrary` e alle relative risorse da una applicazione in modalità console. Richiede che venga aggiunto un riferimento a UILIbrary.dll al progetto di applicazione console.  
  
 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]  
  
 Il codice seguente mostra come sia possibile accedere alla classe `UILibrary` e alle relative risorse da un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Richiede che venga aggiunto un riferimento a UILIbrary.dll al progetto di applicazione Windows Store.  
  
 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]  
  
## <a name="example-localized-includenetportableincludesnet-portable-mdmd"></a>Esempio: [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] localizzata  
 Il seguente esempio di [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] localizzata include le risorse per le impostazioni cultura francesi (Francia) e inglesi (Stati Uniti). Le impostazioni cultura inglese (Stati Uniti) rappresenta impostazioni cultura predefinite dell'app; le risorse vengono illustrate nella tabella di [sezione precedente](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Il file di risorse per le impostazioni cultura francesi (Francia) è denominato LibResources.fr-FR.resx ed è costituito dalle risorse di tipo stringa elencate nella tabella seguente. Il codice sorgente per la classe `UILibrary` è lo stesso di quello riportato nella sezione precedente.  
  
|Nome della risorsa|Valore della risorsa|  
|-------------------|--------------------|  
|Born|Date de naissance|  
|BornLength|20|  
|Hired|Date embauché|  
|HiredLength|16|  
|ID|ID|  
|Nome|Nom|  
|Titolo|Base de données des employés|  
  
 Nell'esempio di codice riportato di seguito viene illustrato come sia possibile accedere alla classe `UILibrary` e alle relative risorse da una applicazione in modalità console. Richiede che venga aggiunto un riferimento a UILIbrary.dll al progetto di applicazione console.  
  
 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]  
  
 Il codice seguente mostra come sia possibile accedere alla classe `UILibrary` e alle relative risorse da un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Richiede che venga aggiunto un riferimento a UILIbrary.dll al progetto di applicazione Windows Store. Usa la proprietà statica `ApplicationLanguages.PrimaryLanguageOverride` per impostare la lingua preferita dell'applicazione in francese.  
  
 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Resources.ResourceManager>  
- [Risorse nelle applicazioni desktop](../../../docs/framework/resources/index.md)  
- [Creazione del pacchetto e distribuzione delle risorse](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
