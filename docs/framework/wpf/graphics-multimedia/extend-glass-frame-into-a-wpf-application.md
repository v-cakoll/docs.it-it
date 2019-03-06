---
title: Estendere l'effetto cristallo a un'applicazione WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: 326cf683c05eae342646efca962cfe9b87ccab79
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364684"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="b03e6-102">Estendere l'effetto cristallo a un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="b03e6-102">Extend Glass Frame Into a WPF Application</span></span>
<span data-ttu-id="b03e6-103">In questo argomento viene illustrato come estendere il [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] fotogramma effetto cristallo all'area client di un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="b03e6-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b03e6-104">Questo esempio funziona solo su un computer [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] che esegue Gestione finestre desktop (DWM) con l'effetto cristallo abilitato.</span><span class="sxs-lookup"><span data-stu-id="b03e6-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> <span data-ttu-id="b03e6-105">Home Basic edition di [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] non supporta la trasparenza effetto cristallo.</span><span class="sxs-lookup"><span data-stu-id="b03e6-105">[!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="b03e6-106">Le aree che avrebbero una trasparenza effetto cristallo nelle altre versioni di [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] risultano opache.</span><span class="sxs-lookup"><span data-stu-id="b03e6-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03e6-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b03e6-107">Example</span></span>  
 <span data-ttu-id="b03e6-108">L'immagine seguente illustra il fotogramma effetto cristallo esteso alla barra degli indirizzi di Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="b03e6-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="b03e6-109">**Internet Explorer con il fotogramma effetto cristallo esteso dietro la barra degli indirizzi.**</span><span class="sxs-lookup"><span data-stu-id="b03e6-109">**Internet Explorer with extended glass frame behind address bar.**</span></span>  
  
 <span data-ttu-id="b03e6-110">![IE7 con il fotogramma effetto cristallo esteso dietro la barra degli indirizzi.](./media/ie7glasstopbar.PNG "IE7glasstopbar")</span><span class="sxs-lookup"><span data-stu-id="b03e6-110">![IE7 with glass frame extended behind address bar.](./media/ie7glasstopbar.PNG "IE7glasstopbar")</span></span>  
  
 <span data-ttu-id="b03e6-111">Per estendere il fotogramma effetto cristallo su un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], è necessario accedere a [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] non gestita.</span><span class="sxs-lookup"><span data-stu-id="b03e6-111">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="b03e6-112">L'esempio di codice seguente esegue Platform Invoke (pinvoke) per le due [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] necessarie per estendere il fotogramma all'area client.</span><span class="sxs-lookup"><span data-stu-id="b03e6-112">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="b03e6-113">Ognuna di queste [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] vengono dichiarate in una classe denominata **NonClientRegionAPI**.</span><span class="sxs-lookup"><span data-stu-id="b03e6-113">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MARGINS  
{  
    public int cxLeftWidth;      // width of left border that retains its size  
    public int cxRightWidth;     // width of right border that retains its size  
    public int cyTopHeight;      // height of top border that retains its size  
    public int cyBottomHeight;   // height of bottom border that retains its size  
};  
  
[DllImport("DwmApi.dll")]  
public static extern int DwmExtendFrameIntoClientArea(  
    IntPtr hwnd,  
    ref MARGINS pMarInset);  
```  
  
```vb  
<StructLayout(LayoutKind.Sequential)>  
        Public Structure MARGINS  
            Public cxLeftWidth As Integer ' width of left border that retains its size  
            Public cxRightWidth As Integer ' width of right border that retains its size  
            Public cyTopHeight As Integer ' height of top border that retains its size  
            Public cyBottomHeight As Integer ' height of bottom border that retains its size  
        End Structure  
  
        <DllImport("DwmApi.dll")>  
        Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer  
        End Function  
```  
  
 <span data-ttu-id="b03e6-114">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) è la funzione DWM che estende il fotogramma all'area client.</span><span class="sxs-lookup"><span data-stu-id="b03e6-114">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="b03e6-115">Il metodo accetta due parametri; un punto di controllo di finestra e una struttura [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins).</span><span class="sxs-lookup"><span data-stu-id="b03e6-115">It takes two parameters; a window handle and a [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) structure.</span></span> <span data-ttu-id="b03e6-116">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) viene usata per indicare a DWM l'ulteriore estensione del fotogramma dell'area client.</span><span class="sxs-lookup"><span data-stu-id="b03e6-116">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03e6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b03e6-117">Example</span></span>  
 <span data-ttu-id="b03e6-118">Per usare la funzione [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea), è necessario ottenere un punto di controllo di finestra.</span><span class="sxs-lookup"><span data-stu-id="b03e6-118">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="b03e6-119">Nelle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], l'handle di finestra può essere ottenuto dal <xref:System.Windows.Interop.HwndSource.Handle%2A> proprietà di un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="b03e6-119">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="b03e6-120">Nell'esempio seguente, il fotogramma viene esteso all'area client nel <xref:System.Windows.FrameworkElement.Loaded> evento della finestra.</span><span class="sxs-lookup"><span data-stu-id="b03e6-120">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>  
  
```csharp  
void OnLoaded(object sender, RoutedEventArgs e)  
{  
   try  
   {  
      // Obtain the window handle for WPF application  
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;  
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);  
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);  
  
      // Get System Dpi  
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);  
      float DesktopDpiX = desktop.DpiX;  
      float DesktopDpiY = desktop.DpiY;  
  
      // Set Margins  
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();  
  
      // Extend glass frame into client area  
      // Note that the default desktop Dpi is 96dpi. The  margins are  
      // adjusted for the system Dpi.  
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));  
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));  
  
      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);  
      //  
      if (hr < 0)  
      {  
         //DwmExtendFrameIntoClientArea Failed  
      }  
   }  
   // If not Vista, paint background white.  
   catch (DllNotFoundException)  
   {  
      Application.Current.MainWindow.Background = Brushes.White;  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="b03e6-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="b03e6-121">Example</span></span>  
 <span data-ttu-id="b03e6-122">Nell'esempio seguente viene illustrata una semplice finestra in cui il fotogramma viene esteso all'area client.</span><span class="sxs-lookup"><span data-stu-id="b03e6-122">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="b03e6-123">Il fotogramma viene esteso dietro il bordo superiore che contiene i due <xref:System.Windows.Controls.TextBox> oggetti.</span><span class="sxs-lookup"><span data-stu-id="b03e6-123">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>  
  
```xaml  
<Window x:Class="SDKSample.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Extended Glass in WPF" Height="300" Width="400"   
    Loaded="OnLoaded" Background="Transparent"  
    >  
  <Grid ShowGridLines="True">  
    <DockPanel Name="mainDock">  
      <!-- The border is used to compute the rendered height with margins.  
           topBar contents will be displayed on the extended glass frame.-->  
      <Border Name="topBar" DockPanel.Dock="Top" >  
        <Grid Name="grid">  
          <Grid.ColumnDefinitions>  
            <ColumnDefinition MinWidth="100" Width="*"/>  
            <ColumnDefinition Width="Auto"/>  
          </Grid.ColumnDefinitions>  
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>  
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>  
        </Grid>  
      </Border>  
      <Grid DockPanel.Dock="Top" >  
        <Grid.ColumnDefinitions>  
          <ColumnDefinition/>  
        </Grid.ColumnDefinitions>  
        <TextBox Grid.Column="0" AcceptsReturn="True"/>  
      </Grid>  
    </DockPanel>  
  </Grid>  
</Window>  
```  
  
 <span data-ttu-id="b03e6-124">Nell'immagine seguente viene illustrato il fotogramma effetto cristallo esteso in un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b03e6-124">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application.</span></span>  
  
 <span data-ttu-id="b03e6-125">**Estensione dell'effetto cristallo a un'applicazione**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **.**</span><span class="sxs-lookup"><span data-stu-id="b03e6-125">**Glass Frame Extended into a**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **Application.**</span></span>  
  
 <span data-ttu-id="b03e6-126">![Estensione dell'effetto cristallo a un'applicazione WPF.](./media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span><span class="sxs-lookup"><span data-stu-id="b03e6-126">![Glass Frame Extended into a WPF application.](./media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03e6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b03e6-127">See also</span></span>
- [<span data-ttu-id="b03e6-128">Panoramica di gestione finestre desktop</span><span class="sxs-lookup"><span data-stu-id="b03e6-128">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="b03e6-129">Cenni preliminari sulla sfocatura Gestione finestre desktop</span><span class="sxs-lookup"><span data-stu-id="b03e6-129">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="b03e6-130">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="b03e6-130">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
