---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614457"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a><span data-ttu-id="a9204-101">Miglioramenti di accessibilità ASP.NET in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a9204-101">ASP.NET Accessibility Improvements in .NET Framework 4.7.1</span></span>

#### <a name="details"></a><span data-ttu-id="a9204-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a9204-102">Details</span></span>

<span data-ttu-id="a9204-103">A partire da .NET Framework 4.7.1, in ASP.NET è stato migliorato il funzionamento dei controlli Web ASP.NET con tecnologia di accessibilità in Visual Studio per supportare al meglio i clienti ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a9204-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="a9204-104">Sono incluse le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9204-104">These include the following changes:</span></span>

- <span data-ttu-id="a9204-105">Modifiche per implementare pattern di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo Aggiungi campo nella procedura guidata DetailsView o la finestra di dialogo Configura ListView nella procedura guidata ListView.</span><span class="sxs-lookup"><span data-stu-id="a9204-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span>
- <span data-ttu-id="a9204-106">Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'Editor campi del pager di dati.</span><span class="sxs-lookup"><span data-stu-id="a9204-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span>
- <span data-ttu-id="a9204-107">Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo Campi nella procedura guidata Modifica campi del pager del controllo DataPager, la finestra di dialogo Configura ObjectContext o la finestra di dialogo Configura selezione dati della procedura guidata Configura origine dati.</span><span class="sxs-lookup"><span data-stu-id="a9204-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selection dialog of the Configure Data Source wizard.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a9204-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="a9204-108">Suggestion</span></span>

<span data-ttu-id="a9204-109">**Come accettare o rifiutare queste modifiche** Per poter usufruire di queste modifiche nella finestra di progettazione di Visual Studio, l'applicazione deve essere eseguita in .NET Framework 4.7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a9204-109">**How to opt in or out of these changes** In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="a9204-110">L'applicazione Web può trarre vantaggio da queste modifiche in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9204-110">The web application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="a9204-111">Installare Visual Studio 2017 15.3 o versione successiva, che supporta le nuove funzionalità di accessibilità con l'opzione di AppContext seguente per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9204-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span>
- <span data-ttu-id="a9204-112">Rifiutare i comportamenti di accessibilità legacy aggiungendo l'`Switch.UseLegacyAccessibilityFeatures`opzione di AppContext alla sezione `<runtime>` del file di configurazione devenv.config e impostandola su `false`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a9204-112">Opt out of the legacy accessibility behaviors by adding the `Switch.UseLegacyAccessibilityFeatures` AppContext switch to the `<runtime>` section in the devenv.exe.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

<span data-ttu-id="a9204-113">Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su `true`.</span><span class="sxs-lookup"><span data-stu-id="a9204-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="a9204-114">Nome</span><span class="sxs-lookup"><span data-stu-id="a9204-114">Name</span></span>    | <span data-ttu-id="a9204-115">Valore</span><span class="sxs-lookup"><span data-stu-id="a9204-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a9204-116">Scope</span><span class="sxs-lookup"><span data-stu-id="a9204-116">Scope</span></span>   | <span data-ttu-id="a9204-117">Minorenne</span><span class="sxs-lookup"><span data-stu-id="a9204-117">Minor</span></span>       |
| <span data-ttu-id="a9204-118">Version</span><span class="sxs-lookup"><span data-stu-id="a9204-118">Version</span></span> | <span data-ttu-id="a9204-119">4.7.1</span><span class="sxs-lookup"><span data-stu-id="a9204-119">4.7.1</span></span>       |
| <span data-ttu-id="a9204-120">Type</span><span class="sxs-lookup"><span data-stu-id="a9204-120">Type</span></span>    | <span data-ttu-id="a9204-121">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="a9204-121">Retargeting</span></span> |
