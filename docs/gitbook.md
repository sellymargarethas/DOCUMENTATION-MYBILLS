
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <meta
            name="viewport"
            content="width=device-width, initial-scale=1"
        />
        <style>
            /* This is needed because the page cover bleed (100vw) will cause horizontal scrolling */
            /* FIXME: use :has once it is ready for Firefox and lift these back to PageSheetView.module.css */
            html,
            body{
                overflow-x: clip;
            }

            body.theme-overlay {
                position: fixed;
                width: 0;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;
                background-color: var(--theme-overlay-background);
                z-index: 10000;
            }

            body.dragging * {
                cursor: grabbing !important;
            }
            .gitbook-splashscreen {
                position: fixed;
                top: 0;
                right: 0;
                bottom: 0;
                left: 0;
                display: flex;
                width: 100%;
                height: 100%;
            }
            .slate-spacer {
                height: 0;
                color: transparent;
                outline: none;
                position: absolute;
            }
        </style>
        <title>Technical and Security Standard - PT Mitra Kasih Perkasa</title><style id="__style-root-primary-color" type="text/css">:root {
                        --custom-theme-color-primary-xxlight: #cddaf6;
--custom-theme-color-primary-xlight: #a9c0f0;
--custom-theme-color-primary-light: #648fe4;
--custom-theme-color-primary-base: #346DDB;
--custom-theme-color-primary-dark: #395794;
--custom-theme-color-primary-xdark: #263b66;
--custom-theme-color-primary-xxdark: #1a202b;
                  }
            </style><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-Bold.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-BoldItalic.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-ExtraBold.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-ExtraBoldItalic.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-Medium.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-MediumItalic.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-Regular.woff2?v=3.19" crossorigin="anonymous"/><link rel="preload" as="font" type="font/woff2" href="https://app.gitbook.com/public/fonts/Inter/Inter-Italic.woff2?v=3.19" crossorigin="anonymous"/><style id="__font-Inter-gitbook-content-font">@font-face {
            font-family: 'gitbook-content-font';
            font-style:  normal;
            font-weight: 700;
            font-display: swap;
            src: local("Inter Bold"), local("Inter-Bold"), url("https://app.gitbook.com/public/fonts/Inter/Inter-Bold.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-Bold.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  italic;
            font-weight: 700;
            font-display: swap;
            src: local("Inter BoldItalic"), local("Inter-BoldItalic"), url("https://app.gitbook.com/public/fonts/Inter/Inter-BoldItalic.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-BoldItalic.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  normal;
            font-weight: 800;
            font-display: swap;
            src: local("Inter ExtraBold"), local("Inter-ExtraBold"), url("https://app.gitbook.com/public/fonts/Inter/Inter-ExtraBold.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-ExtraBold.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  italic;
            font-weight: 800;
            font-display: swap;
            src: local("Inter ExtraBoldItalic"), local("Inter-ExtraBoldItalic"), url("https://app.gitbook.com/public/fonts/Inter/Inter-ExtraBoldItalic.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-ExtraBoldItalic.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  normal;
            font-weight: 500;
            font-display: swap;
            src: local("Inter Medium"), local("Inter-Medium"), url("https://app.gitbook.com/public/fonts/Inter/Inter-Medium.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-Medium.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  italic;
            font-weight: 500;
            font-display: swap;
            src: local("Inter MediumItalic"), local("Inter-MediumItalic"), url("https://app.gitbook.com/public/fonts/Inter/Inter-MediumItalic.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-MediumItalic.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  normal;
            font-weight: 400;
            font-display: swap;
            src: local("Inter Regular"), local("Inter-Regular"), url("https://app.gitbook.com/public/fonts/Inter/Inter-Regular.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-Regular.woff?v=3.19") format("woff");
        }
@font-face {
            font-family: 'gitbook-content-font';
            font-style:  italic;
            font-weight: 400;
            font-display: swap;
            src: local("Inter Italic"), local("Inter-Italic"), url("https://app.gitbook.com/public/fonts/Inter/Inter-Italic.woff2?v=3.19") format("woff2"),
                    url("https://app.gitbook.com/public/fonts/Inter/Inter-Italic.woff?v=3.19") format("woff");
        }</style><meta name="description" content="" id="__meta-description"/><meta name="og:description" content="" id="__meta-og:description"/><meta name="og:image" content="https://app.gitbook.com/share/space/thumbnail/2uNPjhKHrderJ6Wu5nbe.png?color=%23346DDB&amp;logo=&amp;theme=default" id="__meta-og:image"/><meta name="twitter:card" content="summary_large_image" id="__meta-twitter:card"/><meta name="og:title" content="Technical and Security Standard" id="__meta-og:title"/><meta name="twitter:site" content="PT Mitra Kasih Perkasa" id="__meta-twitter:site"/><meta name="robots" content="index" id="__meta-robots"/><link rel="icon" href="https://1802920871-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F2uNPjhKHrderJ6Wu5nbe%2Ficon%2FLudK7xp1ZO4pAVeBWyg1%2Fmkp.png?alt=media&amp;token=fad95c3c-0f25-4e04-9237-554ef9a6eba5" id="__link-icon"/><link rel="preload" as="image" href="https://1802920871-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F2uNPjhKHrderJ6Wu5nbe%2Fuploads%2Fwhz6oeaP6v5R4FcUiCUU%2Fmobile.png?alt=media&amp;token=08205f92-1702-499b-9aab-80072e276b4a"/>
                
                <script type="module" defer src="https://app.gitbook.com/public/app/public-DSJ74OEI.min.js?v=10.9.349-d20c80b850d5e98da3966a9641d3239717c050ba-5292837991"></script>
                <link as="style" rel="preload" href="https://app.gitbook.com/public/app/public-UAEK2C63.css?v=10.9.349-d20c80b850d5e98da3966a9641d3239717c050ba-5292837991">
                <link rel="stylesheet" href="https://app.gitbook.com/public/app/public-UAEK2C63.css?v=10.9.349-d20c80b850d5e98da3966a9641d3239717c050ba-5292837991">
                <style id="react-native-stylesheet">[stylesheet-group="0"]{}
body{margin:0;}
button::-moz-focus-inner,input::-moz-focus-inner{border:0;padding:0;}
html{-ms-text-size-adjust:100%;-webkit-text-size-adjust:100%;-webkit-tap-highlight-color:rgba(0,0,0,0);}
input::-webkit-search-cancel-button,input::-webkit-search-decoration,input::-webkit-search-results-button,input::-webkit-search-results-decoration{display:none;}
[stylesheet-group="1"]{}
.css-11aywtz{-moz-appearance:textfield;-webkit-appearance:none;background-color:rgba(0,0,0,0.00);border-bottom-left-radius:0px;border-bottom-right-radius:0px;border-top-left-radius:0px;border-top-right-radius:0px;border:0 solid black;box-sizing:border-box;font:14px -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;margin:0px;padding:0px;resize:none;}
.css-175oi2r{align-items:stretch;background-color:rgba(0,0,0,0.00);border:0 solid black;box-sizing:border-box;display:flex;flex-basis:auto;flex-direction:column;flex-shrink:0;list-style:none;margin:0px;min-height:0px;min-width:0px;padding:0px;position:relative;text-decoration:none;z-index:0;}
.css-1qaijid{background-color:rgba(0,0,0,0.00);border:0 solid black;box-sizing:border-box;color:inherit;display:inline;font:inherit;list-style:none;margin:0px;padding:0px;text-align:inherit;text-decoration:none;white-space:inherit;word-wrap:break-word;}
.css-1rynq56{background-color:rgba(0,0,0,0.00);border:0 solid black;box-sizing:border-box;color:rgba(0,0,0,1.00);display:inline;font:14px -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;list-style:none;margin:0px;padding:0px;text-align:inherit;text-decoration:none;white-space:pre-wrap;word-wrap:break-word;}
.css-9pa8cd{bottom:0px;height:100%;left:0px;opacity:0;position:absolute;right:0px;top:0px;width:100%;z-index:-1;}
[stylesheet-group="2"]{}
.r-1064s9p{margin:4px;}
.r-11mg6pl{border-bottom-color:rgba(255,255,255,1.00);border-left-color:rgba(255,255,255,1.00);border-right-color:rgba(255,255,255,1.00);border-top-color:rgba(255,255,255,1.00);}
.r-13awgt0{flex:1;}
.r-13fxbef{border-bottom-color:rgba(211,61,61,1.00);border-left-color:rgba(211,61,61,1.00);border-right-color:rgba(211,61,61,1.00);border-top-color:rgba(211,61,61,1.00);}
.r-1471scf{display:inline;}
.r-156hn8l{border-bottom-color:rgba(211,220,228,1.00);border-left-color:rgba(211,220,228,1.00);border-right-color:rgba(211,220,228,1.00);border-top-color:rgba(211,220,228,1.00);}
.r-17gur6a{border-bottom-left-radius:0px;border-bottom-right-radius:0px;border-top-left-radius:0px;border-top-right-radius:0px;}
.r-18c69zk{border-bottom-left-radius:100px;border-bottom-right-radius:100px;border-top-left-radius:100px;border-top-right-radius:100px;}
.r-190qawg{border-bottom-color:rgba(227,232,237,1.00);border-left-color:rgba(227,232,237,1.00);border-right-color:rgba(227,232,237,1.00);border-top-color:rgba(227,232,237,1.00);}
.r-19dn8jc{border-bottom-color:rgba(104,60,17,1.00);border-left-color:rgba(104,60,17,1.00);border-right-color:rgba(104,60,17,1.00);border-top-color:rgba(104,60,17,1.00);}
.r-19nkufj{border-bottom-color:rgba(40,49,67,1.00);border-left-color:rgba(40,49,67,1.00);border-right-color:rgba(40,49,67,1.00);border-top-color:rgba(40,49,67,1.00);}
.r-1awa8pu{border-bottom-color:rgba(101,119,134,1.00);border-left-color:rgba(101,119,134,1.00);border-right-color:rgba(101,119,134,1.00);border-top-color:rgba(101,119,134,1.00);}
.r-1c57tb8{border-bottom-left-radius:34px;border-bottom-right-radius:34px;border-top-left-radius:34px;border-top-right-radius:34px;}
.r-1d4xg89{border-bottom-color:rgba(170,184,194,1.00);border-left-color:rgba(170,184,194,1.00);border-right-color:rgba(170,184,194,1.00);border-top-color:rgba(170,184,194,1.00);}
.r-1dqxon3{overflow-x:auto;overflow-y:auto;}
.r-1edjr5w{padding:80px;}
.r-1f0042m{border-bottom-left-radius:5px;border-bottom-right-radius:5px;border-top-left-radius:5px;border-top-right-radius:5px;}
.r-1fdo3w0{margin:16px;}
.r-1fuqb1j{border-bottom-left-radius:24px;border-bottom-right-radius:24px;border-top-left-radius:24px;border-top-right-radius:24px;}
.r-1j16mh1{border-bottom-left-radius:100%;border-bottom-right-radius:100%;border-top-left-radius:100%;border-top-right-radius:100%;}
.r-1jkafct{border-bottom-left-radius:2px;border-bottom-right-radius:2px;border-top-left-radius:2px;border-top-right-radius:2px;}
.r-1jyn79y{border-bottom-color:rgba(0,150,136,1.00);border-left-color:rgba(0,150,136,1.00);border-right-color:rgba(0,150,136,1.00);border-top-color:rgba(0,150,136,1.00);}
.r-1p0fg95{border-bottom-color:rgba(245,247,249,1.00);border-left-color:rgba(245,247,249,1.00);border-right-color:rgba(245,247,249,1.00);border-top-color:rgba(245,247,249,1.00);}
.r-1phboty{border-bottom-style:solid;border-left-style:solid;border-right-style:solid;border-top-style:solid;}
.r-1rwzld0{border-bottom-color:rgba(11,79,47,1.00);border-left-color:rgba(11,79,47,1.00);border-right-color:rgba(11,79,47,1.00);border-top-color:rgba(11,79,47,1.00);}
.r-1tgwseu{border-bottom-color:rgba(52,109,219,1.00);border-left-color:rgba(52,109,219,1.00);border-right-color:rgba(52,109,219,1.00);border-top-color:rgba(52,109,219,1.00);}
.r-1tw7wh{border-bottom-left-radius:50px;border-bottom-right-radius:50px;border-top-left-radius:50px;border-top-right-radius:50px;}
.r-1udh08x{overflow-x:hidden;overflow-y:hidden;}
.r-1w1o3af{border-bottom-color:rgba(251,232,240,1.00);border-left-color:rgba(251,232,240,1.00);border-right-color:rgba(251,232,240,1.00);border-top-color:rgba(251,232,240,1.00);}
.r-1wgstfn{border-bottom-style:none;border-left-style:none;border-right-style:none;border-top-style:none;}
.r-1x6f3t4{border-bottom-color:rgba(236,243,255,1.00);border-left-color:rgba(236,243,255,1.00);border-right-color:rgba(236,243,255,1.00);border-top-color:rgba(236,243,255,1.00);}
.r-1xc7w19{border-bottom-color:rgba(0,0,0,1.00);border-left-color:rgba(0,0,0,1.00);border-right-color:rgba(0,0,0,1.00);border-top-color:rgba(0,0,0,1.00);}
.r-1xfd6ze{border-bottom-left-radius:8px;border-bottom-right-radius:8px;border-top-left-radius:8px;border-top-right-radius:8px;}
.r-1xutcf9{padding:40px;}
.r-1yadl64{border-bottom-width:0px;border-left-width:0px;border-right-width:0px;border-top-width:0px;}
.r-42olwf{border-bottom-color:rgba(0,0,0,0.00);border-left-color:rgba(0,0,0,0.00);border-right-color:rgba(0,0,0,0.00);border-top-color:rgba(0,0,0,0.00);}
.r-4a18lf{border-bottom-color:rgba(255,0,0,1.00);border-left-color:rgba(255,0,0,1.00);border-right-color:rgba(255,0,0,1.00);border-top-color:rgba(255,0,0,1.00);}
.r-4qtqp9{display:inline-block;}
.r-60ke3l{border-bottom-color:rgba(0,128,0,1.00);border-left-color:rgba(0,128,0,1.00);border-right-color:rgba(0,128,0,1.00);border-top-color:rgba(0,128,0,1.00);}
.r-6578ry{margin:40px;}
.r-6koalj{display:flex;}
.r-6ncur5{border-bottom-left-radius:18px;border-bottom-right-radius:18px;border-top-left-radius:18px;border-top-right-radius:18px;}
.r-6t2glc{border-bottom-left-radius:40px;border-bottom-right-radius:40px;border-top-left-radius:40px;border-top-right-radius:40px;}
.r-9x6qib{border-bottom-color:rgba(204,214,221,1.00);border-left-color:rgba(204,214,221,1.00);border-right-color:rgba(204,214,221,1.00);border-top-color:rgba(204,214,221,1.00);}
.r-ancj0c{border-bottom-color:rgba(218,212,255,1.00);border-left-color:rgba(218,212,255,1.00);border-right-color:rgba(218,212,255,1.00);border-top-color:rgba(218,212,255,1.00);}
.r-by8dw1{margin:24px;}
.r-cdmcib{border-bottom-left-radius:3px;border-bottom-right-radius:3px;border-top-left-radius:3px;border-top-right-radius:3px;}
.r-cpet4d{border-bottom-left-radius:999px;border-bottom-right-radius:999px;border-top-left-radius:999px;border-top-right-radius:999px;}
.r-crgep1{margin:0px;}
.r-d045u9{border-bottom-width:2px;border-left-width:2px;border-right-width:2px;border-top-width:2px;}
.r-d23pfw{padding:24px;}
.r-dta0w2{flex:2;}
.r-edyy15{padding:8px;}
.r-eg6o18{border-bottom-style:dashed;border-left-style:dashed;border-right-style:dashed;border-top-style:dashed;}
.r-egco7n{border-bottom-color:rgba(253,195,137,1.00);border-left-color:rgba(253,195,137,1.00);border-right-color:rgba(253,195,137,1.00);border-top-color:rgba(253,195,137,1.00);}
.r-fx7oqy{border-bottom-color:rgba(0,0,255,1.00);border-left-color:rgba(0,0,255,1.00);border-right-color:rgba(0,0,255,1.00);border-top-color:rgba(0,0,255,1.00);}
.r-gav1f{border-bottom-color:rgba(24,28,31,1.00);border-left-color:rgba(24,28,31,1.00);border-right-color:rgba(24,28,31,1.00);border-top-color:rgba(24,28,31,1.00);}
.r-hvic4v{display:none;}
.r-hwh8t1{margin:8px;}
.r-jqra5g{border-bottom-color:rgba(55,65,81,1.00);border-left-color:rgba(55,65,81,1.00);border-right-color:rgba(55,65,81,1.00);border-top-color:rgba(55,65,81,1.00);}
.r-jxo161{border-bottom-color:rgba(255,204,203,1.00);border-left-color:rgba(255,204,203,1.00);border-right-color:rgba(255,204,203,1.00);border-top-color:rgba(255,204,203,1.00);}
.r-kdyh1x{border-bottom-left-radius:6px;border-bottom-right-radius:6px;border-top-left-radius:6px;border-top-right-radius:6px;}
.r-krxsd3{display:-webkit-box;}
.r-m2nopt{border-bottom-color:rgba(43,46,57,1.00);border-left-color:rgba(43,46,57,1.00);border-right-color:rgba(43,46,57,1.00);border-top-color:rgba(43,46,57,1.00);}
.r-m7id7e{flex:unset;}
.r-m9k8lk{border-bottom-color:rgba(223,255,240,1.00);border-left-color:rgba(223,255,240,1.00);border-right-color:rgba(223,255,240,1.00);border-top-color:rgba(223,255,240,1.00);}
.r-nsbfu8{padding:16px;}
.r-p4pd8u{border-bottom-color:rgba(36,42,49,1.00);border-left-color:rgba(36,42,49,1.00);border-right-color:rgba(36,42,49,1.00);border-top-color:rgba(36,42,49,1.00);}
.r-qwd59z{border-bottom-left-radius:1px;border-bottom-right-radius:1px;border-top-left-radius:1px;border-top-right-radius:1px;}
.r-rs99b7{border-bottom-width:1px;border-left-width:1px;border-right-width:1px;border-top-width:1px;}
.r-t60dpp{padding:0px;}
.r-texgdz{margin:80px;}
.r-tuq35u{padding:4px;}
.r-tyhe3k{border-bottom-left-radius:64px;border-bottom-right-radius:64px;border-top-left-radius:64px;border-top-right-radius:64px;}
.r-xoduu5{display:inline-flex;}
.r-xyw6el{padding:12px;}
.r-ywje51{margin:auto;}
.r-z2wwpe{border-bottom-left-radius:4px;border-bottom-right-radius:4px;border-top-left-radius:4px;border-top-right-radius:4px;}
.r-zhp00w{padding:2px;}
[stylesheet-group="2.1"]{}
.r-10x3wzx{padding-bottom:40px;padding-top:40px;}
.r-11yq8vr{margin-left:40px;margin-right:40px;}
.r-1e081e0{padding-left:12px;padding-right:12px;}
.r-1guathk{padding-left:24px;padding-right:24px;}
.r-1h4fu65{padding-bottom:24px;padding-top:24px;}
.r-1hy1u7s{margin-left:24px;margin-right:24px;}
.r-1isdzm1{padding-left:80px;padding-right:80px;}
.r-1jgb5lz{margin-left:auto;margin-right:auto;}
.r-1p02zvt{padding-left:48px;padding-right:48px;}
.r-1p4rafz{padding-left:2px;padding-right:2px;}
.r-1p6iasa{margin-bottom:4px;margin-top:4px;}
.r-1pn2ns4{padding-left:8px;padding-right:8px;}
.r-1r5su4o{margin-bottom:16px;margin-top:16px;}
.r-1unineu{margin-bottom:40px;margin-top:40px;}
.r-1vvnge1{padding-bottom:2px;padding-top:2px;}
.r-1w3m5we{padding-bottom:80px;padding-top:80px;}
.r-1ybube5{margin-left:8px;margin-right:8px;}
.r-1ydw1k6{margin-left:16px;margin-right:16px;}
.r-1yzf0co{padding-bottom:16px;padding-top:16px;}
.r-4amgru{margin-left:4px;margin-right:4px;}
.r-5njf8e{padding-bottom:8px;padding-top:8px;}
.r-5wp0in{padding-left:40px;padding-right:40px;}
.r-c8eef1{margin-bottom:8px;margin-top:8px;}
.r-g4w12b{padding-left:94px;padding-right:94px;}
.r-g8va3u{margin-left:80px;margin-right:80px;}
.r-lz04qo{margin-left:-4px;margin-right:-4px;}
.r-mgi0kt{margin-left:-24px;margin-right:-24px;}
.r-mk0yit{padding-left:0px;padding-right:0px;}
.r-mvpalk{margin-left:0px;margin-right:0px;}
.r-oyd9sg{padding-bottom:4px;padding-top:4px;}
.r-pw2am6{margin-bottom:24px;margin-top:24px;}
.r-r0h9e2{margin-bottom:0px;margin-top:0px;}
.r-r26ds4{margin-bottom:80px;margin-top:80px;}
.r-rjfia{padding-bottom:0px;padding-top:0px;}
.r-s1qlax{padding-left:4px;padding-right:4px;}
.r-ymttw5{padding-left:16px;padding-right:16px;}
[stylesheet-group="2.2"]{}
.r-100vyta{margin-top:7px;}
.r-1029d6i{top:-24px;}
.r-105ug2t{pointer-events:auto!important;}
.r-109y4c4{height:1px;}
.r-10drpc{color:rgba(0,73,215,1.00);}
.r-10kz8ia{color:rgba(228,79,137,1.00);}
.r-10ptun7{height:16px;}
.r-10pyoum{color:rgba(5,5,5,1.00);}
.r-10sqg0u{margin-bottom:1px;}
.r-10x49cs{font-size:10px;}
.r-10xqauy{padding-top:env(safe-area-inset-top);}
.r-111w7nw{box-shadow:0px 1px 2px rgba(0,0,0,0.69);}
.r-113qch9{cursor:auto;}
.r-116b19x{padding-left:40px;}
.r-119vxgs{border-top-style:dashed;}
.r-11c0sde{margin-top:24px;}
.r-11f42r{height:314px;}
.r-11g3r6m{padding-right:24px;}
.r-11j9u27{visibility:hidden;}
.r-11mo1y0{margin-bottom:7px;}
.r-11mpjr4{background-color:rgba(223,223,223,1.00);}
.r-11udlyb{background-color:rgba(0,150,136,1.00);}
.r-11vxtcu{background-color:rgba(211,220,228,1.00);}
.r-11wlrp9{border-top-color:rgba(52,109,219,1.00);}
.r-11wrixw{margin-left:0px;}
.r-11yh6sk{overflow-x:hidden;}
.r-11ys0m{-webkit-break-before:auto;break-before:auto;}
.r-123mryc{color:rgba(185,94,4,1.00);}
.r-127358a{animation-name:r-9p3sdl;}
.r-127gp16{max-width:150px;}
.r-12dqhl9{height:calc(100vh - 80px);}
.r-12mrs02{object-fit:contain;}
.r-12v2sbk{background-color:rgba(36,42,49,0.50);}
.r-12vffkv>*{pointer-events:auto;}
.r-12vffkv{pointer-events:none!important;}
.r-12ym1je{width:18px;}
.r-12zb1j4{margin-right:7px;}
.r-135wba7{line-height:24px;}
.r-13hce6t{margin-left:4px;}
.r-13i40vn{box-shadow:0px 12px 13px rgba(0,0,0,0.02);}
.r-13i4ljo{width:172px;}
.r-13l2t4g{border-right-width:1px;}
.r-13ll0g2{color:rgba(10,48,105,1.00);}
.r-13lvk87{margin-left:110px;}
.r-13qz1uu{width:100%;}
.r-13tjlyg{transition-duration:0.1s;}
.r-13yce4e{border-top-width:0px;}
.r-142tt33{-webkit-text-decoration-line:line-through;text-decoration-line:line-through;}
.r-144uupt{left:2px;}
.r-146iojx{max-width:300px;}
.r-1472mwg{height:24px;}
.r-14792hc{left:-64px;}
.r-14bkmb3{bottom:-3px;}
.r-14eup4l{top:3px;}
.r-14gqq1x{margin-top:4px;}
.r-14lw9ot{background-color:rgba(255,255,255,1.00);}
.r-14sbq61{background-color:rgba(33,150,243,1.00);}
.r-14utu6a{line-height:8px;}
.r-14vq63g{background-color:rgba(3,58,22,1.00);}
.r-14yzgew{line-height:18px;}
.r-150rngu{-webkit-overflow-scrolling:touch;}
.r-157h22z{background-color:rgba(45,50,58,1.00);}
.r-15czi30{background-image:linear-gradient(90deg, #e44f89, #c62c68);}
.r-15d4u6f{background-color:rgba(145,176,240,1.00);}
.r-15g7tld{margin-bottom:80px;}
.r-15m1z73{margin-left:40px;}
.r-15n4387{outline-color:#2662d7;}
.r-15o5oer{bottom:auto;}
.r-15ysp7h{min-height:32px;}
.r-15zivkp{margin-bottom:4px;}
.r-16dba41{font-weight:400;}
.r-16l9doz{height:auto;}
.r-16vg0q1{max-width:225px;}
.r-16y2uox{flex-grow:1;}
.r-173mn98{align-self:flex-end;}
.r-1777fci{justify-content:center;}
.r-17bb2tj{animation-duration:0.75s;}
.r-17giqoz{box-shadow:0px 0px 7px rgba(0,0,0,0.52);}
.r-17grq5a{margin-right:-8px;}
.r-17leim2{background-repeat:repeat;}
.r-17rnw9f{line-height:30px;}
.r-17s6mgv{justify-content:flex-end;}
.r-17tb59b{opacity:0.7;}
.r-17tloay{opacity:0.6;}
.r-17wrw06{color:rgba(180,26,26,1.00);}
.r-184en5c{z-index:1;}
.r-18ayb63{border-right-color:rgba(227,232,237,1.00);}
.r-18kxxzh{flex-grow:0;}
.r-18nhz7w{top:-3px;}
.r-18p6if4{border-right-width:2px;}
.r-18u37iz{flex-direction:row;}
.r-18y5qoh{color:rgba(165,214,255,1.00);}
.r-190thrv{color:rgba(145,75,5,1.00);}
.r-19554kt{width:90px;}
.r-19907ok{-moz-transition:opacity ease 200ms;-webkit-transition:opacity ease 200ms;transition:opacity ease 200ms;}
.r-19akecc{color:rgba(175,245,180,1.00);}
.r-19byhck{flex-basis:32%;}
.r-19lq7b1{top:16px;}
.r-19r33im{letter-spacing:1.2px;}
.r-19tq15n{margin-top:80px;}
.r-19wmn03{width:20px;}
.r-19z077z{touch-action:none;}
.r-1a3cspq{background-color:rgba(40,49,67,1.00);}
.r-1abnn5w{animation-play-state:paused;}
.r-1acpoxo{width:36px;}
.r-1aeqstq{cursor:-webkit-grabbing;cursor:-moz-grabbing;cursor:grabbing;}
.r-1aerykh{border-top-color:rgba(211,220,228,1.00);}
.r-1aockid{width:40px;}
.r-1armvtb{font-size:8px;}
.r-1awozwy{align-items:center;}
.r-1axcl7z{border:1px solid #d3dce4;}
.r-1ay1djp{animation-duration:1s;}
.r-1b00too{background-color:rgba(236,239,241,1.00);}
.r-1b096ap{border-bottom-color:rgba(36,42,49,1.00);}
.r-1b1g84l{bottom:-8px;}
.r-1b3fm86{background-color:undefined;}
.r-1b43r93{font-size:14px;}
.r-1bcbbo8{color:rgba(17,99,41,1.00);}
.r-1bnj018{color:rgba(92,105,117,1.00);}
.r-1bwbpp8{color:rgba(57,87,148,1.00);}
.r-1bwgafa{-webkit-text-decoration-color:rgba(136,153,168,1.00);text-decoration-color:rgba(136,153,168,1.00);}
.r-1c681wc{color:rgba(77,222,152,1.00);}
.r-1c6unfx{forced-color-adjust:none;}
.r-1ce3o0f{max-height:80vh;}
.r-1ceczpf{min-height:24px;}
.r-1clhhh9{-moz-transition-property:all;-webkit-transition-property:all;transition-property:all;}
.r-1cmwbt1{gap:8px;}
.r-1d09ksm{align-items:baseline;}
.r-1d2f490{left:0px;}
.r-1d4mawv{margin-right:4px;}
.r-1d5kdc7{flex-direction:column-reverse;}
.r-1d7fvdj{justify-content:space-evenly;}
.r-1d9grui{border-bottom-color:rgba(211,220,228,1.00);}
.r-1ddef8g{-webkit-text-decoration-line:underline;text-decoration-line:underline;}
.r-1dernwh{height:70%;}
.r-1dlgt49{max-height:30px;}
.r-1dmvmgl{background-color:rgba(36,42,49,1.00);}
.r-1dn12g7{line-height:48px;}
.r-1dpl46z{border-bottom-right-radius:4px;}
.r-1dqbpge{cursor:text;}
.r-1dumtqg{background-color:rgba(253,195,137,1.00);}
.r-1e1gmzv{color:rgba(38,59,102,1.00);}
.r-1efo1hp{border-bottom-color:rgba(43,46,57,1.00);}
.r-1ei5mc7{cursor:inherit;}
.r-1eic64l{color:rgba(198,44,104,1.00);}
.r-1enofrn{font-size:12px;}
.r-1etz4cy{color:rgba(194,217,255,1.00);}
.r-1euycsn{flex-direction:row-reverse;}
.r-1ewcgjf{box-shadow:0px 1px 3px rgba(0,0,0,0.5);}
.r-1f2v84d{color:rgba(204,207,212,1.00);}
.r-1f4ipl0{left:29px;}
.r-1f529hi{line-height:14px;}
.r-1fd96xs{padding-left:50px;}
.r-1fdih9r{gap:24px;}
.r-1fe0xdi{left:0%;}
.r-1ff274t{text-align:right;}
.r-1fi01yr{background-color:rgba(55,65,81,1.00);}
.r-1fiaf3z{opacity:0.05;}
.r-1fo40xd{top:80px;}
.r-1fq43b1{flex-basis:100%;}
.r-1g7fiml{height:30px;}
.r-1g80fh1{margin-right:80px;}
.r-1ghhsy9{color:rgba(52,109,219,1.00);}
.r-1gigy5k{border-bottom-color:rgba(45,50,58,1.00);}
.r-1glc72y{border-bottom-color:rgba(245,247,249,1.00);}
.r-1glkqn6{width:80px;}
.r-1h0z5md{justify-content:flex-start;}
.r-1h815vi{right:92%;}
.r-1h8ys4a{padding-top:4px;}
.r-1h9q8wt{color:rgba(69,69,69,1.00);}
.r-1habvwh{align-items:flex-start;}
.r-1hjwoze{height:18px;}
.r-1hlnpa{height:3px;}
.r-1hpgsb4{;}
.r-1hqdnve{box-shadow:0px 0px 4px inset rgba(0,0,0, 0.08);}
.r-1hrvmjx{border-top-color:rgba(55,65,81,1.00);}
.r-1hvjb8t{padding-right:4px;}
.r-1hy97zq{padding-top:80px;}
.r-1hycxz{width:350px;}
.r-1i6wzkk{-moz-transition-property:opacity;-webkit-transition-property:opacity;transition-property:opacity;}
.r-1i7sdiz{box-shadow:0px 4px 10px rgba(0,0,0,0.05);}
.r-1i93rbr{right:0%;}
.r-1ielgck{animation-duration:300ms;}
.r-1ifxtd0{margin-bottom:16px;}
.r-1ik5qf4{max-width:500px;}
.r-1iln25a{word-wrap:normal;}
.r-1ioqa4e{border-top-right-radius:7px;}
.r-1ipicw7{width:300px;}
.r-1j7aebl{width:880px;}
.r-1janqcz{width:16px;}
.r-1jg9483{width:8px;}
.r-1jj8364{margin-left:auto;}
.r-1jkjb{margin-left:8px;}
.r-1jnzvcq{padding-bottom:80px;}
.r-1jocfgc{width:290px;}
.r-1jpmnxg{word-wrap:anywhere;}
.r-1jrm8ja{background-color:rgba(185,94,4,1.00);}
.r-1jsra8{box-shadow:inset 0px 0px 0px 1px #e3e8ed;}
.r-1jxfwug{border-top-width:2px;}
.r-1k1q3bj{max-height:300px;}
.r-1k25im9{height:26px;}
.r-1kb76zh{margin-right:8px;}
.r-1kf75xu{color:rgba(12,105,61,1.00);}
.r-1kfrs79{font-weight:600;}
.r-1ki14p2{top:10px;}
.r-1kihuf0{align-self:center;}
.r-1kjq87h{width:376px;}
.r-1knl56f{animation-name:r-1hunrpy;}
.r-1kvn7zp{max-height:150px;}
.r-1kx0pzc{background-image:radial-gradient(rgba(0, 0, 0, 0.1), #181c1f);}
.r-1l0m7dr{background-image:radial-gradient(rgba(0, 0, 0, 0.1), #ffffff);}
.r-1l7z4oj{padding-bottom:16px;}
.r-1l94q7l{box-shadow:inset 0px 0px 1px rgb(0 0 0 / 30%);}
.r-1ld3bg{top:-4px;}
.r-1ldzwu0{animation-timing-function:linear;}
.r-1ljd8xs{border-left-width:1px;}
.r-1lky6n1{background-color:rgba(227,232,237,1.00);}
.r-1lnfjr6{-webkit-background-clip:text;}
.r-1lnt56z{color:rgba(211,220,228,1.00);}
.r-1loqt21{cursor:pointer;}
.r-1m04atk{padding-left:8px;}
.r-1m4drjs{top:-6px;}
.r-1maqer6{max-width:860px;}
.r-1md8qp7{right:-40px;}
.r-1mdbw0j{padding-bottom:0px;}
.r-1mdsxwj{color:rgba(237,159,81,1.00);}
.r-1mgmw1x{background-image:linear-gradient(90deg, #5f45ff, #442fc8);}
.r-1mhb1uw{width:42px;}
.r-1mhtwjo{left:-3px;}
.r-1mlwlqe{flex-basis:auto;}
.r-1mnahxq{margin-top:0px;}
.r-1moh23t{bottom:16px;}
.r-1mrlafo{background-position:0;}
.r-1ms9ukt{bottom:-5px;}
.r-1mtwht8{color:rgba(210,168,255,1.00);}
.r-1muvv40{animation-iteration-count:infinite;}
.r-1n20pny{width:140px;}
.r-1n6k3lk{color:rgba(36,42,49,1.00);}
.r-1na1l7e{animation-play-state:running;}
.r-1nf4jbm{color:rgba(59,69,78,1.00);}
.r-1niwhzg{background-color:rgba(0,0,0,0.00);}
.r-1nj16ve{left:-10px;}
.r-1nlw0im{bottom:8px;}
.r-1nq9s1i{color:rgba(145,176,240,1.00);}
.r-1ny4l3l{outline-style:none;}
.r-1o9jcv2{max-width:660px;}
.r-1ocf4r9{scroll-snap-type:y mandatory;}
.r-1odw9d6{background-color:rgba(20,23,28,1.00);}
.r-1oec5bt{opacity:0.2;}
.r-1oep0n4{left:-12px;}
.r-1ois7e2{color:rgba(55,65,81,1.00);}
.r-1or9b2r{height:10px;}
.r-1osy6ei{color:rgba(255,220,215,1.00);}
.r-1oszu61{align-items:stretch;}
.r-1otgn73{touch-action:manipulation;}
.r-1ow6zhx{margin-left:16px;}
.r-1oy60ga{transform:translateX(-12px);}
.r-1p0dtai{bottom:0px;}
.r-1p3vkdf{border-right-color:rgba(45,50,58,1.00);}
.r-1p5i0ed{bottom:-24px;}
.r-1p69tiw{border-top-color:rgba(43,46,57,1.00);}
.r-1peese0{margin-bottom:24px;}
.r-1ph75f1{height:80px;}
.r-1pi2tsx{height:100%;}
.r-1pl7oy7{min-height:48px;}
.r-1pos5eu{vertical-align:middle;}
.r-1ptriwd{right:2px;}
.r-1pyaxff{padding-right:8px;}
.r-1q142lx{flex-shrink:0;}
.r-1q3nxaj{z-index:300;}
.r-1q6j1ae{right:-88px;}
.r-1q6rxnj{padding-right:110px;}
.r-1q77oe7{background-color:rgba(171,183,202,1.00);}
.r-1q9jyb7{-webkit-filter:blur(16px) contrast(110%) hue-rotate(10deg) brightness(1.2) saturate(1.2);filter:blur(16px) contrast(110%) hue-rotate(10deg) brightness(1.2) saturate(1.2);}
.r-1qc3rpd{transform:scaleY(-1);}
.r-1qd0xha{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;}
.r-1qdbj55{animation-name:r-ndfo3d;}
.r-1qefu2b{right:-3px;}
.r-1qhn6m8{padding-left:16px;}
.r-1quu1zo{;}
.r-1r0uwd5{color:rgba(255,166,87,1.00);}
.r-1r74h94{left:8px;}
.r-1r8g8re{height:36px;}
.r-1rasi3h{color:rgba(136,153,168,1.00);}
.r-1rbj2e8{outline-color:#f5f7f9;}
.r-1rdth4h{border-left-color:rgba(55,65,81,1.00);}
.r-1rho1gz{box-shadow:0px 12px 13px rgba(0,0,0,0.12);}
.r-1rkdych{max-width:1040px;}
.r-1rla0r3{background-image:linear-gradient(90deg, #d33d3d, #b41a1a);}
.r-1rnoaur{overflow-y:auto;}
.r-1ro0kt6{flex-basis:0%;}
.r-1ro7rbe{right:100%;}
.r-1rttkqs{width:400px;}
.r-1rxb9bi{row-gap:4px;}
.r-1s3egr7{z-index:100;}
.r-1s8p94s{max-width:832px;}
.r-1sc18lr{padding-bottom:88px;}
.r-1sncvnh{transform:translateZ(0px);}
.r-1sxrcry{background-size:auto;}
.r-1t2qqvi{flex-basis:50%;}
.r-1t7uo4s{object-fit:cover;}
.r-1t8m4kl{text-shadow:0px 0px 3px rgba(36,42,49,1.00);}
.r-1ta3fxp{-webkit-column-gap:8px;column-gap:8px;}
.r-1tazni7{cursor:not-allowed;}
.r-1ts5s6y{aspect-ratio:1.7777777777777777;}
.r-1ttybm1{border-top-color:rgba(45,50,58,1.00);}
.r-1ty4vvm{left:40px;}
.r-1tymxbh{box-shadow:5px 0px 7px rgba(36,42,49,0.60);}
.r-1u8kdu{bottom:24px;}
.r-1ua3vzd{background-color:rgba(223,255,240,1.00);}
.r-1ub1aon{transform:translateY(100%);}
.r-1udbk01{text-overflow:ellipsis;}
.r-1ufdtu9{background-image:linear-gradient(270deg, #e3e8ed 10%, #f5f7f9, #e3e8ed 90%);}
.r-1ufr4wv{z-index:9;}
.r-1ug9s38{box-shadow:inset 0px 0px 0px 1px #374151;}
.r-1ui5ee8{font-size:32px;}
.r-1ul06mb{margin-left:32px;}
.r-1ulgld5{color:rgba(255,123,114,1.00);}
.r-1uql0sn{top:-1.2em;}
.r-1ur9v65{padding-top:40px;}
.r-1ut4w64{margin-bottom:-1px;}
.r-1uwte3a{padding-bottom:40px;}
.r-1uypc71{animation-timing-function:ease-in;}
.r-1v2oles{top:50%;}
.r-1v4p587{border-bottom-color:rgba(24,28,31,1.00);}
.r-1v6e3re{min-width:48px;}
.r-1v7fmog{background-color:rgba(236,243,255,1.00);}
.r-1v7sw2p{background-size:50% 80px;}
.r-1vamr63{max-width:720px;}
.r-1vckr1u{background-color:rgba(245,247,249,1.00);}
.r-1vex5ub{color:rgba(68,47,200,1.00);}
.r-1vo7ria{color:rgba(38,98,215,1.00);}
.r-1vutw0s{background-color:rgba(103,6,12,1.00);}
.r-1vz48go{background-image:radial-gradient(rgba(255, 255, 255, 0.1), #181c1f);}
.r-1vzi8xi{vertical-align:middle;}
.r-1w2pmg{height:0px;}
.r-1w6e6rj{flex-wrap:wrap;}
.r-1wan564{color:rgba(169,192,240,1.00);}
.r-1wb8bfx{text-decoration-thickness:2px;}
.r-1wbh5a2{flex-shrink:1;}
.r-1wezhl{margin-left:80px;}
.r-1wfhzrg{height:120px;}
.r-1wghi3f{top:-8px;}
.r-1wtj0ep{justify-content:space-between;}
.r-1wv73ep{align-self:baseline;}
.r-1ww30s9{max-width:30px;}
.r-1wyvozj{left:50%;}
.r-1wyyakw{z-index:-1;}
.r-1wzrnnt{margin-top:16px;}
.r-1x35g6{font-size:24px;}
.r-1xbve24{height:6px;}
.r-1xcajam{position:fixed;}
.r-1xnzce8{-moz-user-select:text;-webkit-user-select:text;user-select:text;}
.r-1xoqk23{background-color:rgba(68,47,200,1.00);}
.r-1y14msn{border-bottom-color:rgba(55,65,81,1.00);}
.r-1y9xkqr{left:8%;}
.r-1yb8zos{background-color:rgba(162,169,185,1.00);}
.r-1ybp48z{background-image:linear-gradient(90deg, #cc3131, #b41a1a);}
.r-1ye8kvj{max-width:600px;}
.r-1ygmrgt{padding-top:24px;}
.r-1ylffjs{-webkit-text-decoration-style:dotted;text-decoration-style:dotted;}
.r-1yv4afn{border-top-color:rgba(227,232,237,1.00);}
.r-1yvhtrz{width:32px;}
.r-1yxedwg{top:8px;}
.r-1yyzdbt{border-left-color:rgba(227,232,237,1.00);}
.r-257lmc{width:1180px;}
.r-29dh1f{background-image:linear-gradient(90deg, #eceff1, #e3e8ed);}
.r-2awvau{min-width:-webkit-max-content;min-width:-moz-max-content;min-width:max-content;}
.r-2eszeu::-webkit-scrollbar{display:none}
.r-2eszeu{scrollbar-width:none;}
.r-2fm7cc{color:rgba(139,148,158,1.00);}
.r-2fw26j{outline-offset:0px;}
.r-2jelyo{background-color:rgba(24,28,31,1.00);}
.r-2jxp4q{background-color:rgba(34,39,46,1.00);}
.r-2kxcpj{inset:0px;}
.r-2llsf{min-height:100%;}
.r-2o02ov{margin-top:40px;}
.r-2tavb8{background-color:rgba(0,0,0,0.60);}
.r-2zpn8w{-webkit-break-inside:avoid;break-inside:avoid;}
.r-30o5oe{-moz-appearance:none;-ms-appearance:none;-webkit-appearance:none;appearance:none;}
.r-30qeir{bottom:-4px;}
.r-36ujnk{font-style:italic;}
.r-37tt59{line-height:32px;}
.r-3da1kt{height:8px;}
.r-3dgjpp{border-top-color:rgba(36,42,49,1.00);}
.r-3hw5f6{color:rgba(149,56,0,1.00);}
.r-3mc0re{right:8px;}
.r-3mtglp{row-gap:16px;}
.r-3o833n{background-color:rgba(251,232,240,1.00);}
.r-3pxcvb{border-bottom-color:rgba(255,255,255,1.00);}
.r-3s2u2q{white-space:nowrap;}
.r-417010{z-index:0;}
.r-41syhy{max-width:504px;}
.r-432wen{width:3px;}
.r-44c749{border-bottom-left-radius:7px;}
.r-493a2x{width:680px;}
.r-4c3hy2{max-width:245px;}
.r-4d76ec{height:200px;}
.r-4dj0k7{box-shadow:0px 1px 2px rgba(0,0,0,0.12);}
.r-4gszlv{background-size:cover;}
.r-4jz4xt{background-image:linear-gradient(90deg, #374151, #374151);}
.r-4v7adb{height:5px;}
.r-59fiw0{max-width:416px;}
.r-5cpxsl{stroke-width:3;}
.r-5is6sd{max-width:460px;}
.r-5kkj8d{border-top-width:1px;}
.r-5ks0hp{right:3.5px;}
.r-5kx3fr{page-break-inside:avoid;}
.r-5oul0u{margin-bottom:8px;}
.r-5soawk{width:10px;}
.r-5xr8s6{outline-width:2px;}
.r-60emj1{background-color:rgba(255,204,203,1.00);}
.r-61z16t{margin-right:0px;}
.r-633pao{pointer-events:none!important;}
.r-6b6lzv{color:rgba(100,143,228,1.00);}
.r-6dt33c{opacity:1;}
.r-6k4xqk{margin-top:-40px;}
.r-6t5ypu{border-bottom-left-radius:4px;}
.r-6taxm2:-ms-input-placeholder{color:var(--placeholderTextColor);opacity:1;}
.r-6taxm2::-moz-placeholder{color:var(--placeholderTextColor);opacity:1;}
.r-6taxm2::-webkit-input-placeholder{color:var(--placeholderTextColor);opacity:1;}
.r-6taxm2::placeholder{color:var(--placeholderTextColor);opacity:1;}
.r-6uxfom{margin-left:24px;}
.r-6wscbn{max-width:252px;}
.r-73dpzl{border-top-color:rgba(245,247,249,1.00);}
.r-7b7h2f{left:100%;}
.r-7bxf49{background-color:rgba(205,218,246,1.00);}
.r-7cikom{font-size:inherit;}
.r-7l9xyp{background-color:rgba(255,255,255,0.20);}
.r-7q8q6z{cursor:default;}
.r-7xmw5f{width:-webkit-fit-content;width:-moz-fit-content;width:fit-content;}
.r-81rbui{animation-name:r-1ak6360;}
.r-855088{border-left-color:rgba(0,0,0,0.00);}
.r-88pszg{margin-right:16px;}
.r-8akbws{-webkit-box-orient:vertical;}
.r-8d26hk{margin-bottom:40px;}
.r-8hc5te{width:6px;}
.r-8jwyv6{-moz-transition:opacity 0.2s ease-in-out;-webkit-transition:opacity 0.2s ease-in-out;transition:opacity 0.2s ease-in-out;}
.r-8upyzv{width:260px;}
.r-8v5hsd{color:rgba(126,231,135,1.00);}
.r-9030i9{box-shadow:0px 4px 10px rgba(0,0,0,0.99);}
.r-9111t9{padding-right:410px;}
.r-92ng3h{width:1px;}
.r-934yyj{padding-left:34px;}
.r-9358xi{background-color:rgba(35,131,226,0.14);}
.r-95jzfe{padding-top:16px;}
.r-97e31f{padding-bottom:env(safe-area-inset-bottom);}
.r-97prym{flex-basis:16px;}
.r-99m41f{color:rgba(110,119,129,1.00);}
.r-9aemit{padding-right:0px;}
.r-9ji8r7{transform:translateY(0%);}
.r-9jpwak{min-width:auto;}
.r-a21fva{box-shadow:0px -1px 2px rgba(0,0,0,0.69);}
.r-a2tzq0{justify-content:space-around;}
.r-a5pmau{margin-right:2px;}
.r-a9hzal{height:660px;}
.r-adacv{min-height:64px;}
.r-adyw6z{font-size:20px;}
.r-ah5dr5>*{pointer-events:none;}
.r-ah5dr5{pointer-events:auto!important;}
.r-ak0haq{color:rgba(121,192,255,1.00);}
.r-aqxs90{-moz-transition:opacity 500ms ease-in, z-index 1000ms ease-in;-webkit-transition:opacity 500ms ease-in, z-index 1000ms ease-in;transition:opacity 500ms ease-in, z-index 1000ms ease-in;}
.r-ar5de{height:112px;}
.r-b4cb4{max-height:440px;}
.r-b88u0q{font-weight:700;}
.r-bcqeeo{min-width:0px;}
.r-bcycc3{box-shadow:0px -1px 2px rgba(0,0,0,0.12);}
.r-bgnin{min-width:150px;}
.r-bnwqim{position:relative;}
.r-bsjocg{@media print:[object Object];}
.r-bta5j5{right:40px;}
.r-buy8e9{overflow-y:hidden;}
.r-bv2aro{padding-left:env(safe-area-inset-left);}
.r-bxaprw{border-top-left-radius:7px;}
.r-c68hjy{color:rgba(161,161,161,1.00);}
.r-c8fpu0{background-color:rgba(0,136,71,1.00);}
.r-cb7i37{outline-color:#395794;}
.r-cdhzog{padding-right:80px;}
.r-cpa5s6{scroll-snap-align:start;}
.r-d822y2{color:rgba(5,80,174,1.00);}
.r-deolkf{box-sizing:border-box;}
.r-dflpy8{height:1.2em;}
.r-dkge59{background-color:rgba(170,184,194,1.00);}
.r-dnmrzs{max-width:100%;}
.r-dse9kg{outline-style:auto;}
.r-dvzd6p{right:-1px;}
.r-dvzwsg{border-left-color:rgba(211,220,228,1.00);}
.r-dwliz8{border-left-width:2px;}
.r-e1k2in{right:16px;}
.r-e9uq0i{animation-duration:1200ms;}
.r-ea455c{border:none;}
.r-eafdt9{transition-duration:0.15s;}
.r-ecifi{max-width:970px;}
.r-ehq7j7{background-size:contain;}
.r-epq5cr{height:2px;}
.r-eqo98v{top:24px;}
.r-eqz5dr{flex-direction:column;}
.r-ero68b{min-height:40px;}
.r-eu3ka{height:40px;}
.r-f4gmv6{gap:16px;}
.r-fa5tdg{max-width:456px;}
.r-fdjqy7{text-align:left;}
.r-flmpir{border-bottom-color:rgba(40,49,67,1.00);}
.r-fnigne{border-right-width:0px;}
.r-fpub7{color:rgba(0,0,0,0.00);}
.r-g3mlsw{animation-name:r-t2lo5v;}
.r-gg6oyi{font-family:gitbook-content-font,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;}
.r-ggadg3{left:-2px;}
.r-givd4m{left:-5px;}
.r-gl891g{min-width:420px;}
.r-gpge5b{right:calc(50% + 11px);}
.r-gtdqiz{position:-webkit-sticky;position:sticky;}
.r-gu0qjt{padding-left:32px;}
.r-gxnn5r{border-left-width:0px;}
.r-gxopl6{left:316px;}
.r-gy4na3{padding-left:0px;}
.r-gys0vz{color:rgba(0,136,71,1.00);}
.r-h1b427{width:225px;}
.r-h2mvr{min-width:8px;}
.r-h2q2x{transform:scaleX(-1);}
.r-h3s6tt{height:48px;}
.r-h7ga17{background-color:rgba(43,46,57,1.00);}
.r-h7gdob{color:currentColor;}
.r-ha54is{icon-color:#a2a9b9;}
.r-hauab{-moz-transition:width 50ms ease-in-out;-webkit-transition:width 50ms ease-in-out;transition:width 50ms ease-in-out;}
.r-hbpseb{line-height:22px;}
.r-hd655f{color:rgba(162,169,185,1.00);}
.r-homxoj{color:inherit;}
.r-hq6u89{left:92%;}
.r-hqnlqz{border-left-color:rgba(52,109,219,1.00);}
.r-htfu76{margin-left:-8px;}
.r-hu79xy{min-width:196px;}
.r-hvns9x{max-width:400px;}
.r-hxflta{padding-right:env(safe-area-inset-right);}
.r-i023vh{padding-right:16px;}
.r-i7h7g2{-webkit-backdrop-filter:blur(5px);backdrop-filter:blur(5px);}
.r-i8xx8x{color:rgba(207,34,46,1.00);}
.r-ia06lx{background-color:rgba(115,92,255,1.00);}
.r-ibjss6{background-color:rgba(136,153,168,1.00);}
.r-icoktb{opacity:0.5;}
.r-ifefl9{min-height:0px;}
.r-ihd41t{border:1px solid #374151;}
.r-iphfwy{padding-bottom:4px;}
.r-ipm5af{top:0px;}
.r-iqs06e{background-image:radial-gradient(rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 1));}
.r-ir6n1k{border-top-right-radius:6px;}
.r-ixzivm{@media print:[object Object];}
.r-iyfy8q{width:auto;}
.r-j300sb{animation-name:r-1rx4pb;}
.r-jfrpv2{color:rgba(130,80,223,1.00);}
.r-jn0m22{top:54px;}
.r-jn5ml{right:-5px;}
.r-jvuzdy{top:-5px;}
.r-jwli3a{color:rgba(255,255,255,1.00);}
.r-jxjwwx{left:24px;}
.r-k200y{align-self:flex-start;}
.r-k923pl{background-color:rgba(218,212,255,1.00);}
.r-kcufgn{cursor:ew-resize;}
.r-key0ze{height:240px;}
.r-kicko2{border-top-left-radius:4px;}
.r-kls4rr{padding-right:40px;}
.r-knv0ih{margin-top:8px;}
.r-kquydp{right:-4px;}
.r-ky29hr{bottom:2px;}
.r-l0gwng{width:200px;}
.r-l13dpy{z-index:200;}
.r-l27s25{background-color:rgba(204,207,212,1.00);}
.r-l9hqf4{box-shadow:0px 1px 1px rgba(0,0,0,0.69);}
.r-l9st2p{-webkit-text-decoration-color:rgba(162,169,185,1.00);text-decoration-color:rgba(162,169,185,1.00);}
.r-labphf{height:-webkit-fit-content;height:-moz-fit-content;height:fit-content;}
.r-lchren{margin-right:auto;}
.r-lk1fr1{icon-color:#8899a8;}
.r-lltvgl{overflow-x:auto;}
.r-lqms97{margin-left:-1px;}
.r-lrsllp{width:24px;}
.r-lrvibr{-moz-user-select:none;-webkit-user-select:none;user-select:none;}
.r-lv5dtd{padding-left:110px;}
.r-lx1l9k{background-image:radial-gradient(rgba(255, 255, 255, 0.1), #ffffff);}
.r-m0vln2{border-left-color:rgba(43,46,57,1.00);}
.r-m2pi6t{padding-left:4px;}
.r-m5arl1{width:2px;}
.r-mabqd8{height:32px;}
.r-majxgm{font-weight:500;}
.r-mbgqwd{margin-right:24px;}
.r-mfh4gg{scroll-snap-type:x mandatory;}
.r-mfzc6t{background-color:rgba(0,0,0,0.10);}
.r-mhe3cw{z-index:10;}
.r-ms8t9i{border-left-width:3px;}
.r-mwitap{pointer-event:none;}
.r-na6qhi{;}
.r-ng8e2f{cursor:-webkit-grab;cursor:-moz-grab;cursor:grab;}
.r-nkouq2{box-shadow:-5px 0px 7px rgba(36,42,49,0.60);}
.r-notknq{border-top-right-radius:4px;}
.r-nvplwv{animation-timing-function:ease-out;}
.r-nvvorq{top:3.5px;}
.r-nwxazl{line-height:40px;}
.r-nzcix3{border-bottom-color:rgba(227,232,237,1.00);}
.r-o2ldwd{left:calc(50% + 11px);}
.r-o8yidv{border-top-left-radius:6px;}
.r-o9xkwf{top:2px;}
.r-obd0qt{align-items:flex-end;}
.r-onxxid{background-color:rgba(27,30,33,0.77);}
.r-op3p1c{width:520px;}
.r-orgf3d{opacity:0;}
.r-ou6ah9{border-top-left-radius:0px;}
.r-oucylx{border-bottom-color:rgba(0,0,0,0.00);}
.r-oz83uh{box-shadow:0px 1px 1px rgba(0,0,0,0.12);}
.r-p1pxzi{margin-bottom:0px;}
.r-pex7a0{color:rgba(130,7,30,1.00);}
.r-pi8zqv{box-shadow:0px 0px 7px rgba(0,0,0,0.04);}
.r-pm9dpa{max-height:100%;}
.r-puj83k{padding-left:24px;}
.r-py1axk{border-bottom-right-radius:7px;}
.r-q4m81j{text-align:center;}
.r-qklmqi{border-bottom-width:1px;}
.r-ql8eny{min-height:200px;}
.r-qn3fzs{padding-bottom:24px;}
.r-qyrhsv{border-right-color:rgba(40,49,67,1.00);}
.r-r1s0sa{background-color:rgba(255,235,233,1.00);}
.r-r7ey0d{background-color:rgba(218,212,255,0.50);}
.r-r9hte5{-webkit-backdrop-filter:blur(10px);backdrop-filter:blur(10px);}
.r-rs94m5{background-image:url("data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9Im5vIj8+CjxzdmcKICAgeG1sbnM6ZGM9Imh0dHA6Ly9wdXJsLm9yZy9kYy9lbGVtZW50cy8xLjEvIgogICB4bWxuczpjYz0iaHR0cDovL2NyZWF0aXZlY29tbW9ucy5vcmcvbnMjIgogICB4bWxuczpyZGY9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkvMDIvMjItcmRmLXN5bnRheC1ucyMiCiAgIHhtbG5zOnN2Zz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIKICAgdmVyc2lvbj0iMS4xIgogICB2aWV3Qm94PSIwIDAgMSAxIgogICBwcmVzZXJ2ZUFzcGVjdFJhdGlvPSJ4TWluWU1pbiBtZWV0Ij4KICA8cGF0aAogICAgIGQ9Ik0gMC4wNDAzODA1OSwwLjYyNjc3NjcgMC4xNDY0NDY2MSwwLjUyMDcxMDY4IDAuNDI5Mjg5MzIsMC44MDM1NTMzOSAwLjMyMzIyMzMsMC45MDk2MTk0MSB6IE0gMC4yMTcxNTcyOSwwLjgwMzU1MzM5IDAuODUzNTUzMzksMC4xNjcxNTcyOSAwLjk1OTYxOTQxLDAuMjczMjIzMyAwLjMyMzIyMzMsMC45MDk2MTk0MSB6IgogICAgIGlkPSJyZWN0Mzc4MCIKICAgICBzdHlsZT0iZmlsbDojZmZmZmZmO2ZpbGwtb3BhY2l0eToxO3N0cm9rZTpub25lIiAvPgo8L3N2Zz4K");}
.r-rwqe4o{width:48px;}
.r-s09aw7{background-image:linear-gradient(to left, #735cff, rgb(109 28 169), rgb(96 104 191), #008847, #FFD139, #b95e04, #d33d3d);}
.r-s0e3za{padding-left:80px;}
.r-sa2ff0{min-height:100vh;}
.r-sfbmgh{z-index:9999;}
.r-sga3zk{height:64px;}
.r-sgscqh{width:250px;}
.r-t12b5v{border-top-right-radius:0px;}
.r-t3lkjx{background-color:rgba(228,79,137,1.00);}
.r-t9hbny{background-color:rgba(211,61,61,1.00);}
.r-tceitz{left:16px;}
.r-tni569{background-color:rgba(11,79,47,1.00);}
.r-tskmnb{padding-top:8px;}
.r-tsynxw{text-transform:uppercase;}
.r-u529wo{transform:translateY(-2px);}
.r-u6sd8q{background-repeat:no-repeat;}
.r-u8s1d{position:absolute;}
.r-u92y06{background-color:rgba(255,165,0,1.00);}
.r-u9bbvc{;}
.r-u9z937{bottom:80px;}
.r-ubezar{font-size:16px;}
.r-ud0q2t{letter-spacing:1px;}
.r-ufs8t{background-clip:text;}
.r-uibjmv{font-family:gitbook-code-font, Menlo, monospace;}
.r-upfvwg{box-shadow:0px 0px 1px rgb(255 255 255 / 30%);}
.r-uweo6c{bottom:136px;}
.r-ux9zog{background-color:rgba(51,61,85,1.00);}
.r-v2u3o6{right:4px;}
.r-v5byei{top:-12px;}
.r-vjwmdu{max-width:75px;}
.r-vkv6oe{min-width:40px;}
.r-vlcob{color:rgba(24,28,31,1.00);}
.r-vq47rg{color:rgba(211,61,61,1.00);}
.r-vvn4in{background-position:center;}
.r-w0va4e{margin-right:40px;}
.r-w9n8ly{transition-delay:200ms;}
.r-wc24c3{z-index:20;}
.r-wech8c{max-width:1280px;}
.r-wgabs5{border-bottom-width:2px;}
.r-wk8lta{padding-top:0px;}
.r-ws9h79{left:4px;}
.r-wwqw7s{left:-1px;}
.r-wy61xf{height:72px;}
.r-x1dlf0{max-width:200px;}
.r-x3cy2q{background-size:100% 100%;}
.r-xb2eav{font-size:40px;}
.r-xbwjba{border-bottom-color:rgba(52,109,219,1.00);}
.r-xd6kpl{padding-bottom:8px;}
.r-xifl00{left:-4px;}
.r-xky0vn{background-color:rgba(104,60,17,1.00);}
.r-xnn892{background-color:rgba(218,251,225,1.00);}
.r-xx3c9p{animation-name:r-imtty0;}
.r-xzortm{margin-right:-16px;}
.r-y3rmyz{width:120px;}
.r-ye2ihm{background-image:none;}
.r-yh6aho{background-image:linear-gradient(270deg, #2b2e39 10%, #22272e, #2b2e39 90%);}
.r-yj30ev{right:24px;}
.r-yrgyi6{white-space:pre;}
.r-ywxogp{color:rgba(115,92,255,1.00);}
.r-z3s97b{border-right-color:rgba(43,46,57,1.00);}
.r-z80fyv{height:20px;}
.r-z9jf92{color:rgba(234,242,247,1.00);}
.r-zchlnj{right:0px;}
.r-zh076v{height:100vh;}
.r-zits6j{right:8%;}
.r-znv4k7{border-right-color:rgba(52,109,219,1.00);}
.r-zo7nv5{-webkit-column-gap:16px;column-gap:16px;}
.r-ztyd71{background-color:rgba(0,0,0,0.20);}
@-webkit-keyframes r-1ak6360{0%{background-position-x:0%;}100%{background-position-x:100%;}}
@-webkit-keyframes r-1hunrpy{0%{transform:translateY(100%);}100%{transform:translateY(0%);}}
@-webkit-keyframes r-1rx4pb{0%{transform:translateX(-100%);}100%{transform:translateX(400%);}}
@-webkit-keyframes r-9p3sdl{0%{transform:rotate(0deg);}100%{transform:rotate(360deg);}}
@-webkit-keyframes r-imtty0{0%{opacity:0;}100%{opacity:1;}}
@-webkit-keyframes r-ndfo3d{0%{transform:translateY(0%);}100%{transform:translateY(100%);}}
@-webkit-keyframes r-t2lo5v{0%{opacity:1;}100%{opacity:0;}}
@keyframes r-1ak6360{0%{background-position-x:0%;}100%{background-position-x:100%;}}
@keyframes r-1hunrpy{0%{transform:translateY(100%);}100%{transform:translateY(0%);}}
@keyframes r-1rx4pb{0%{transform:translateX(-100%);}100%{transform:translateX(400%);}}
@keyframes r-9p3sdl{0%{transform:rotate(0deg);}100%{transform:rotate(360deg);}}
@keyframes r-imtty0{0%{opacity:0;}100%{opacity:1;}}
@keyframes r-ndfo3d{0%{transform:translateY(0%);}100%{transform:translateY(100%);}}
@keyframes r-t2lo5v{0%{opacity:1;}100%{opacity:0;}}
[stylesheet-group="10"]{}
[data-rnwrdesktop-18u37iz]{flex-direction:row;}
[data-rnwrdesktop-1hy97zq-1q6rxnj-lv5dtd-]{padding-left:110px;padding-right:110px;padding-top:80px;}
[data-rnwrdesktop-1ph75f1]{height:80px;}
[data-rnwrdesktop-1uwte3a]{padding-bottom:40px;}
[data-rnwrdesktop-gg6oyi-ubezar-135wba7-1kfrs79]{font-family:gitbook-content-font,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;font-size:16px;font-weight:600;line-height:24px;}
[data-rnwrdesktop-gg6oyi-xb2eav-1dn12g7-b88u0q]{font-family:gitbook-content-font,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;font-size:40px;font-weight:700;line-height:48px;}
[data-rnwrdesktop-h3s6tt]{height:48px;}
[data-rnwrdesktop-hidden]{display: none;}
[data-rnwrdesktop-iyfy8q-1qhn6m8-11g3r6m-1h0z5md]{justify-content:flex-start;padding-left:16px;padding-right:24px;width:auto;}
[data-rnwrdesktop-visible]{display: flex;}
[stylesheet-group="11"]{}
@media (max-width: 1024px) and (max-width: 9999999.494850524510111312253100114px) { [data-rnwr1024-eqz5dr] {flex-direction:column;} }
@media (max-width: 1024px) and (max-width: 9999999.49485052454910510212011610048px) { [data-rnwr1024-1ifxtd0] {margin-bottom:16px;} }
@media (max-width: 1490px) and (max-width: 9999999.495257484511810511510598108101px) { [data-rnwr1490-visible] {display: flex;} }
@media (max-width: 1490px) and (max-width: 9999999.49525748454955555510299105px) { [data-rnwr1490-1777fci] {justify-content:center;} }
[stylesheet-group="12"]{}
@media (max-width: 700px) and (max-width: 9999999.5548484510111312253100114px) { [data-rnwr700-eqz5dr] {flex-direction:column;} }
@media (max-width: 700px) and (max-width: 9999999.55484845103103541111211054511798101122971144549515311998975545491071021141155557px) { [data-rnwr700-gg6oyi-ubezar-135wba7-1kfrs79] {font-family:gitbook-content-font,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;font-size:16px;font-weight:600;line-height:24px;} }
@media (max-width: 700px) and (max-width: 9999999.55484845103103541111211054549117105531011015645110119120971221084598565611748113px) { [data-rnwr700-gg6oyi-1ui5ee8-nwxazl-b88u0q] {font-family:gitbook-content-font,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;font-size:32px;font-weight:700;line-height:40px;} }
@media (max-width: 700px) and (max-width: 9999999.55484845104105100100101110px) { [data-rnwr700-hidden] {display: none;} }
@media (max-width: 700px) and (max-width: 9999999.5548484510512110212156113451011175110797px) { [data-rnwr700-iyfy8q-eu3ka] {height:40px;width:auto;} }
@media (max-width: 700px) and (max-width: 9999999.5548484510512110212156113451031215211097514510548505111810445491199810453975045491044812253109100454910610710698px) { [data-rnwr700-iyfy8q-gy4na3-i023vh-1wbh5a2-1h0z5md-1jkjb] {flex-shrink:1;justify-content:flex-start;margin-left:8px;padding-left:0px;padding-right:16px;width:auto;} }
@media (max-width: 700px) and (max-width: 9999999.554848451151039751122107px) { [data-rnwr700-sga3zk] {height:64px;} }
@media (max-width: 700px) and (max-width: 9999999.5548484511810511510598108101px) { [data-rnwr700-visible] {display: flex;} }
@media (max-width: 700px) and (max-width: 9999999.55484845491195410154114106454955555510299105px) { [data-rnwr700-1w6e6rj-1777fci] {flex-wrap:wrap;justify-content:center;} }
@media (max-width: 700px) and (max-width: 9999999.5548484557531061221021014549113104110541095645105485051118104px) { [data-rnwr700-95jzfe-1qhn6m8-i023vh] {padding-left:16px;padding-right:16px;padding-top:16px;} }
@media (max-width: 970px) and (max-width: 9999999.5755484510111312253100114px) { [data-rnwr970-eqz5dr] {flex-direction:column;} }
[stylesheet-group="13"]{}
@media (max-width: 700px) and (max-width: 9999999.554848454955555510299105px) { [data-rnwr700-1777fci] {justify-content:center;} }
[stylesheet-group="20"]{}
[data-rnwi-handle="nearest"] [data-rnwinearest-1nf4jbm-]{color:rgba(59,69,78,1.00);}
body:not(.dragging) [data-rnwi--1ghhsy9-hover-focus]:hover, body:not(.dragging) [data-rnwi--1ghhsy9-hover-focus]:focus{color:rgba(52,109,219,1.00);}
body:not(.dragging) [data-rnwi--1tgwseu--focus]:focus{border-bottom-color:rgba(52,109,219,1.00);border-left-color:rgba(52,109,219,1.00);border-right-color:rgba(52,109,219,1.00);border-top-color:rgba(52,109,219,1.00);}
body:not(.dragging) [data-rnwi-190qawg-hover-focus]:hover, body:not(.dragging) [data-rnwi-190qawg-hover-focus]:focus{border-bottom-color:rgba(227,232,237,1.00);border-left-color:rgba(227,232,237,1.00);border-right-color:rgba(227,232,237,1.00);border-top-color:rgba(227,232,237,1.00);}
body:not(.dragging) [data-rnwi-1vckr1u-hover-focus]:hover, body:not(.dragging) [data-rnwi-1vckr1u-hover-focus]:focus{background-color:rgba(245,247,249,1.00);}
body:not(.dragging) [data-rnwi-5xr8s6-dse9kg-2fw26j-15n4387-focus-visible]:focus-visible{outline-color:#2662d7;outline-offset:0px;outline-style:auto;outline-width:2px;}
body:not(.dragging) [data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible]:focus-visible{outline-color:#395794;outline-offset:0px;outline-style:auto;outline-width:2px;}
body:not(.dragging) [data-rnwi-handle="BaseCard"]:hover [data-rnwibasecard--1ghhsy9-hover-focus], body:not(.dragging) [data-rnwi-handle="BaseCard"]:focus [data-rnwibasecard--1ghhsy9-hover-focus]{color:rgba(52,109,219,1.00);}
body:not(.dragging) [data-rnwi-handle="BaseCard"]:hover [data-rnwibasecard--1ghhsy9-hover]{color:rgba(52,109,219,1.00);}
body:not(.dragging) [data-rnwi-handle="button"]:hover [data-rnwibutton--1ghhsy9-hover-focus], body:not(.dragging) [data-rnwi-handle="button"]:focus [data-rnwibutton--1ghhsy9-hover-focus]{color:rgba(52,109,219,1.00);}
body:not(.dragging) [data-rnwi-handle="button"]:hover [data-rnwibutton-1bnj018-hover-focus], body:not(.dragging) [data-rnwi-handle="button"]:focus [data-rnwibutton-1bnj018-hover-focus]{color:rgba(92,105,117,1.00);}
body:not(.dragging) [data-rnwi-handle="nearest"]:hover [data-rnwinearest--1ghhsy9-hover-focus], body:not(.dragging) [data-rnwi-handle="nearest"]:focus [data-rnwinearest--1ghhsy9-hover-focus]{color:rgba(52,109,219,1.00);}
body:not(.dragging) [data-rnwi-handle="nearest"]:hover [data-rnwinearest-1nf4jbm-hover-focus], body:not(.dragging) [data-rnwi-handle="nearest"]:focus [data-rnwinearest-1nf4jbm-hover-focus]{color:rgba(59,69,78,1.00);}
body:not(.dragging) [data-rnwi-u529wo-aq1qub-c1zw6o-1khlhp8-1cut0bx-na6qhi--hover]:hover{box-shadow:0px 12px 13px rgba(0,0,0,0.02);transform:translateY(-2px);}</style>
                <style>
                    html,
                    body {
                        -webkit-font-smoothing: antialiased;
                        text-rendering: optimizelegibility;
                        width: 100%;
                        min-height: 100vh;
                        user-select: none;
                        outline: none;
                        position: relative;
                    }
                    /* Avoid Chrome to see Safari hack */
                    @supports (-webkit-touch-callout: none) {
                        html,
                        body,
                        .gitbook-root {
                            /* The hack for Safari */
                            min-height: -webkit-fill-available;
                        }
                    }
                    .gitbook-root {
                        display: flex;
                        min-height: 100vh;
                    }
                </style>
            
        <script type="text/javascript" defer src="https://cdn.iframe.ly/embed.js" async></script>
        <script
            type="text/javascript"
            defer
            src="https://cdn.polyfill.io/v2/polyfill.js?features=Intl.~locale.en"
            crossorigin="anonymous"
        ></script>

    </head>
    <body class="theme-color-light theme-radius-rounded">
        <script>
                    (function () {
                        var theme = null;

                        try {
                          var rawValue = localStorage.getItem("@gitbook/themeMode");
                          if (rawValue !== null) {
                            theme = JSON.parse(rawValue);
                          }
                        } catch (err) {
                          // Make an attempt in case it's not a JSON value
                          if (theme !== "light" && theme !== "dark") {
                            theme = null;
                          }
                        }
                        if (undefined && theme && theme !== "undefined") {
                          document.body.classList.add("theme-overlay");
                          document.body.classList.remove("theme-color-undefined");
                          document.body.classList.add("theme-color-" + theme);
                        }
                      })();
                </script>
                   <div class="gitbook-root"><div class="css-175oi2r r-13awgt0 r-12vffkv"><div class="css-175oi2r r-13awgt0 r-12vffkv"><!--$--><header data-rnwrdesktop-1ph75f1="true" data-rnwr700-sga3zk="true" class="r-1xc7w19 r-1phboty r-1yadl64 r-deolkf r-6koalj r-1mlwlqe r-1q142lx r-crgep1 r-ifefl9 r-bcqeeo r-t60dpp r-nzcix3 r-qklmqi r-gtdqiz r-ipm5af r-184en5c r-18u37iz r-1awozwy" style="background-color:rgba(255,255,255,1.00)"><div class="view_SggA- flex_jZskO publicContainer_11UZS smallHorizontal_kBCzR alignCenter_zl3iW withStickyHeader_HQiM-"><a href="/mkp-mobile/" aria-label="PT Mitra Kasih Perkasa" data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible="true" data-rnwi-handle="nearest" data-rnwrdesktop-iyfy8q-1qhn6m8-11g3r6m-1h0z5md="true" data-rnwr700-iyfy8q-gy4na3-i023vh-1wbh5a2-1h0z5md-1jkjb="true" class="css-175oi2r r-1i6wzkk r-lrvibr r-1loqt21 r-1otgn73 r-18u37iz r-1awozwy" style="transition-duration:0.15s" data-testid="public.headerHomeLink"><div class="css-175oi2r r-6wscbn r-1ro0kt6 r-16y2uox r-1wbh5a2 r-18u37iz r-1h0z5md r-1awozwy"><div class="css-175oi2r"><div data-rnwrdesktop-visible="true" data-rnwr700-hidden="true" class="css-175oi2r"><div class="css-175oi2r r-18u37iz r-1awozwy r-1777fci r-z2wwpe r-88pszg" style="width:40px;height:40px;overflow-x:hidden;overflow-y:hidden"><img alt="" src="https://www.gitbook.com/cdn-cgi/image/width=40,dpr=2,height=40,fit=contain,format=auto/https%3A%2F%2F1802920871-files.gitbook.io%2F~%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F2uNPjhKHrderJ6Wu5nbe%252Ficon%252FLudK7xp1ZO4pAVeBWyg1%252Fmkp.png%3Falt%3Dmedia%26token%3Dfad95c3c-0f25-4e04-9237-554ef9a6eba5" width="100%" height="auto" decoding="async" class="r-1pi2tsx r-12mrs02 r-13qz1uu r-1ro0kt6 r-16y2uox r-1wbh5a2"/></div></div><div data-rnwrdesktop-hidden="true" data-rnwr700-visible="true" class="css-175oi2r"><div class="css-175oi2r r-18u37iz r-1awozwy r-1777fci r-z2wwpe r-88pszg" style="width:24px;height:24px;overflow-x:hidden;overflow-y:hidden"><img alt="" src="https://www.gitbook.com/cdn-cgi/image/width=24,dpr=2,height=24,fit=contain,format=auto/https%3A%2F%2F1802920871-files.gitbook.io%2F~%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F2uNPjhKHrderJ6Wu5nbe%252Ficon%252FLudK7xp1ZO4pAVeBWyg1%252Fmkp.png%3Falt%3Dmedia%26token%3Dfad95c3c-0f25-4e04-9237-554ef9a6eba5" width="100%" height="auto" decoding="async" class="r-1pi2tsx r-12mrs02 r-13qz1uu r-1ro0kt6 r-16y2uox r-1wbh5a2"/></div></div></div><div dir="auto" data-rnwrdesktop-gg6oyi-ubezar-135wba7-1kfrs79="true" data-rnwr700-gg6oyi-ubezar-135wba7-1kfrs79="true" class="css-1rynq56 r-1udh08x"><span data-rnwinearest-1nf4jbm-="true" data-rnwinearest--1ghhsy9-hover-focus="true" data-rnwi-handle="nearest" class="css-1qaijid r-8akbws r-krxsd3 r-dnmrzs r-1udh08x r-1udbk01" style="-webkit-line-clamp:2;color:rgba(59,69,78,1.00)">PT Mitra Kasih Perkasa</span></div></div></a><div data-rnwr700-hidden="true" class="css-175oi2r r-18u37iz r-17s6mgv r-1awozwy r-1ro0kt6 r-16y2uox r-1wbh5a2 r-1qhn6m8"></div><div data-rnwrdesktop-visible="true" data-rnwr700-hidden="true" class="css-175oi2r r-1jj8364 r-puj83k r-1pyaxff r-16vg0q1 r-1ro0kt6 r-16y2uox r-1wbh5a2"><div aria-label="Search" data-rnwi-190qawg-hover-focus="true" data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible="true" data-rnwi-handle="nearest" tabindex="0" class="css-175oi2r r-1i6wzkk r-lrvibr r-1loqt21 r-1otgn73 r-42olwf r-kdyh1x r-rs99b7 r-eu3ka r-13qz1uu r-18u37iz r-1wtj0ep r-1awozwy r-1qhn6m8 r-1pyaxff" style="background-color:rgba(59,69,78,0.10);transition-duration:0.15s"><div class="css-175oi2r r-18u37iz r-1awozwy"><svg viewBox="0 0 24 24" fill="none" preserveAspectRatio="xMidYMid meet" class="r-1kb76zh" style="vertical-align:middle;width:16px;height:16px;color:rgba(59,69,78,1.00)"><path fill-rule="evenodd" clip-rule="evenodd" d="M10.5 4a6.5 6.5 0 100 13 6.5 6.5 0 000-13zM2 10.5a8.5 8.5 0 1117 0 8.5 8.5 0 01-17 0z" fill="currentColor"></path><path fill-rule="evenodd" clip-rule="evenodd" d="M15.093 15.093a1 1 0 011.414 0l5.2 5.2a1 1 0 01-1.414 1.414l-5.2-5.2a1 1 0 010-1.414z" fill="currentColor"></path></svg><div dir="auto" data-rnwinearest-1nf4jbm-hover-focus="true" data-rnwi-handle="nearest" class="css-1rynq56 r-gg6oyi r-1b43r93 r-16dba41 r-hbpseb" style="color:rgba(59,69,78,1.00)">Search</div></div><div class="css-175oi2r"><span class="base_UAIdb shortcut_2Blls xsmallHorizontal_j9kFq base_UAIdb groupTitle_xV-vG flex_jZskO row_PhhRi alignCenter_zl3iW main_Iciyi">⌃K</span></div></div></div><div data-rnwrdesktop-hidden="true" data-rnwr700-visible="true" class="css-175oi2r r-1jj8364 r-puj83k r-1pyaxff"><div aria-label="Search" role="button" data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible="true" data-rnwi-handle="button" tabindex="0" class="css-175oi2r r-1i6wzkk r-lrvibr r-1loqt21 r-1otgn73 r-1awozwy r-42olwf r-rs99b7 r-18u37iz r-18kxxzh r-1777fci r-1ny4l3l r-z2wwpe r-mabqd8 r-1bnj018 r-mk0yit r-1yvhtrz" style="transition-duration:0.15s"><svg viewBox="0 0 24 24" fill="none" preserveAspectRatio="xMidYMid meet" data-rnwibutton--1ghhsy9-hover-focus="true" data-rnwi-handle="nearest" style="vertical-align:middle;width:16px;height:16px;color:rgba(59,69,78,1.00)"><path fill-rule="evenodd" clip-rule="evenodd" d="M10.5 4a6.5 6.5 0 100 13 6.5 6.5 0 000-13zM2 10.5a8.5 8.5 0 1117 0 8.5 8.5 0 01-17 0z" fill="currentColor"></path><path fill-rule="evenodd" clip-rule="evenodd" d="M15.093 15.093a1 1 0 011.414 0l5.2 5.2a1 1 0 01-1.414 1.414l-5.2-5.2a1 1 0 010-1.414z" fill="currentColor"></path></svg></div></div></div></header><div data-rnwrdesktop-hidden="true" data-rnwr700-visible="true" class="css-175oi2r"></div><div data-rnwrdesktop-18u37iz="true" data-rnwr700-eqz5dr="true" class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2 r-14lw9ot"><div class="view_SggA- flex_jZskO publicContainer_11UZS"><div class="css-175oi2r r-13awgt0" style="background-color:rgba(255,255,255,1.00)"><!--$--><div class="view_SggA- flex_jZskO pageCoverBleedFull_eqtqd"></div><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2 r-18u37iz"><div class="view_SggA- flex_jZskO pageWrapper_ca2kA flex1_aMpAE column_C3yiR"><main class="r-1oszu61 r-1xc7w19 r-1phboty r-1yadl64 r-deolkf r-6koalj r-crgep1 r-ifefl9 r-bcqeeo r-t60dpp r-bnwqim r-417010 r-1ro0kt6 r-16y2uox r-1wbh5a2 r-eqz5dr"><div class="view_SggA- flex_jZskO blockWrapper_y0Ubs"><div data-rnwr1490-1777fci="true" class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2 r-18u37iz"><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2"><div class="css-175oi2r r-eqz5dr r-1ygmrgt r-1peese0"><div class="css-175oi2r r-18u37iz"><div data-rnwrdesktop-h3s6tt="true" data-rnwr700-iyfy8q-eu3ka="true" class="css-175oi2r r-18u37iz r-17s6mgv r-1awozwy"></div><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2"><h1 data-rnwrdesktop-gg6oyi-xb2eav-1dn12g7-b88u0q="true" data-rnwr700-gg6oyi-1ui5ee8-nwxazl-b88u0q="true" class="r-1xnzce8 r-crgep1 r-1nf4jbm" data-testid="page.title">Technical and Security Standard</h1></div><div data-rnwrdesktop-hidden="true" data-rnwr1490-visible="true" data-rnwr700-visible="true" class="css-175oi2r r-18u37iz r-1awozwy"><div aria-label="Page actions" role="button" data-rnwi-1vckr1u-hover-focus="true" data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible="true" data-rnwi-handle="button" tabindex="0" class="css-175oi2r r-1i6wzkk r-lrvibr r-1loqt21 r-1otgn73 r-1awozwy r-42olwf r-rs99b7 r-18u37iz r-18kxxzh r-1777fci r-1ny4l3l r-eu3ka r-1bnj018 r-18c69zk r-mk0yit r-1aockid" style="transition-duration:0.15s" data-testid="pageCompactToolbar.paletteButton"><svg viewBox="0 0 16 16" fill="none" preserveAspectRatio="xMidYMid meet" data-rnwibutton-1bnj018-hover-focus="true" data-rnwi-handle="nearest" class="r-h7gdob" style="vertical-align:middle;width:18px;height:18px"><path d="M8 2.4a1.1 1.1 0 100 2.2 1.1 1.1 0 000-2.2zM8 6.9a1.1 1.1 0 100 2.2 1.1 1.1 0 000-2.2zM8 11.4a1.1 1.1 0 100 2.2 1.1 1.1 0 000-2.2z" fill="currentColor"></path></svg></div></div></div><div class="css-175oi2r r-1wzrnnt"></div></div></div></div></div><div data-rnwrdesktop-1uwte3a="true" class="css-175oi2r"><div class="css-175oi2r r-bnwqim"><div data-testid="page.contentEditor" data-slate-editor="true" data-document-key="828aafae9adc4a0ba4063d4f64a0a27d" data-key="828aafae9adc4a0ba4063d4f64a0a27d" autoCorrect="on" spellcheck="true" style="outline:none;white-space:pre-wrap;word-wrap:break-word"><div><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2"><div data-rnwr1490-1777fci="true" data-rnwr700-1777fci="true" class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2 r-18u37iz r-1777fci"><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2"><div class="css-175oi2r"><div class="css-175oi2r"><div data-key="0248d2ea769c410898975a5b2f5812b7" class="view_SggA- flex_jZskO block_UxARL mediumVertical_-Vaii mediumTop_QDiZG mediumBottom_jdYUb"><div data-block-content="0248d2ea769c410898975a5b2f5812b7" class="r-1oszu61 r-1xc7w19 r-1phboty r-1yadl64 r-deolkf r-6koalj r-eqz5dr r-crgep1 r-ifefl9 r-bcqeeo r-t60dpp r-bnwqim r-417010 r-1ro0kt6 r-16y2uox r-1wbh5a2"><div data-rnwr700-1w6e6rj-1777fci="true" class="css-175oi2r r-18u37iz r-1777fci r-zo7nv5 r-3mtglp"><div data-slate-void="true" data-key="fc73fb6c76e44bfc9391a61a21303a0e"><div><div class="css-175oi2r r-1awozwy r-1ro0kt6 r-16y2uox r-1wbh5a2"><div class="css-175oi2r r-z2wwpe r-bnwqim" style="max-width:100%;max-height:100%"><div data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible="true" data-rnwi-handle="nearest" tabindex="0" class="css-175oi2r r-1i6wzkk r-lrvibr r-1loqt21 r-1otgn73 r-1awozwy" style="transition-duration:0.15s"><img alt="MKP Mobile" src="https://1802920871-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F2uNPjhKHrderJ6Wu5nbe%2Fuploads%2Fwhz6oeaP6v5R4FcUiCUU%2Fmobile.png?alt=media&amp;token=08205f92-1702-499b-9aab-80072e276b4a" width="100%" height="auto" decoding="async" class="r-z2wwpe r-dnmrzs"/></div></div></div></div></div></div></div></div></div></div></div></div></div></div></div></div><div class="view_SggA- flex_jZskO blockWrapper_y0Ubs"><div data-rnwr1490-1777fci="true" class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2 r-18u37iz r-11c0sde"><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2"><div class="css-175oi2r"><div data-rnwrdesktop-18u37iz="true" data-rnwr970-eqz5dr="true" class="css-175oi2r r-1peese0"><a href="/mkp-mobile/technical-and-security-standard/introduction" data-rnwi-u529wo-aq1qub-c1zw6o-1khlhp8-1cut0bx-na6qhi--hover="true" data-rnwi--1tgwseu--focus="true" data-rnwi-5xr8s6-dse9kg-2fw26j-cb7i37-focus-visible="true" data-rnwi-handle="BaseCard" class="css-175oi2r r-lrvibr r-1loqt21 r-1otgn73 r-190qawg r-z2wwpe r-rs99b7 r-1udh08x r-1clhhh9 r-18u37iz r-1awozwy r-nsbfu8 r-1ro0kt6 r-16y2uox r-1wbh5a2" style="background-color:rgba(255,255,255,1.00);transition-duration:0.15s"><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2"><div class="css-175oi2r"><div dir="auto" class="css-1rynq56 r-gg6oyi r-1enofrn r-16dba41 r-14yzgew r-1rasi3h">Next</div></div><div dir="auto" data-rnwibasecard--1ghhsy9-hover-focus="true" data-rnwi-handle="nearest" class="css-1rynq56 r-dnmrzs r-1udh08x r-1udbk01 r-3s2u2q r-1iln25a r-gg6oyi r-ubezar r-135wba7 r-majxgm r-1nf4jbm">Introduction</div></div><div class="css-175oi2r r-1ow6zhx"><svg viewBox="0 0 16 16" fill="none" preserveAspectRatio="xMidYMid meet" data-rnwibasecard--1ghhsy9-hover="true" data-rnwi-handle="nearest" class="r-1rasi3h" style="vertical-align:middle;width:24px;height:24px"><path fill-rule="evenodd" clip-rule="evenodd" d="M9.076 3.576a.6.6 0 01.848 0l4 4a.6.6 0 010 .848l-4 4a.6.6 0 01-.848-.848L12.052 8.6H2.5a.6.6 0 010-1.2h9.552L9.076 4.424a.6.6 0 010-.848z" fill="currentColor"></path></svg></div></a></div><div class="css-175oi2r r-1ygmrgt r-1yv4afn r-5kkj8d"><div data-rnwrdesktop-18u37iz="true" data-rnwr1024-eqz5dr="true" class="css-175oi2r r-1awozwy r-1wtj0ep"><div data-rnwr1024-1ifxtd0="true" class="css-175oi2r"><div dir="auto" class="css-1rynq56 r-1rasi3h r-gg6oyi r-1b43r93 r-16dba41 r-hbpseb">Last modified <span aria-label="2023-06-16 16:32 UTC" class="css-1qaijid">2d ago</span></div></div><div class="css-175oi2r"><div class="css-175oi2r"><a href="https://www.gitbook.com/?utm_source=content&amp;utm_medium=trademark&amp;utm_campaign=2uNPjhKHrderJ6Wu5nbe" data-rnwi--1ghhsy9-hover-focus="true" data-rnwi-5xr8s6-dse9kg-2fw26j-15n4387-focus-visible="true" data-rnwi-handle="nearest" class="css-175oi2r r-1i6wzkk r-lrvibr r-1loqt21 r-1otgn73 r-18u37iz r-1awozwy r-1niwhzg" style="transition-duration:0.15s"><svg viewBox="0 0 1000 1000" fill="none" preserveAspectRatio="xMidYMid meet" data-rnwi--1ghhsy9-hover-focus="true" data-rnwi-5xr8s6-dse9kg-2fw26j-15n4387-focus-visible="true" data-rnwi-handle="nearest" class="r-1rasi3h" style="vertical-align:middle;width:40px;height:40px"><path fill-rule="evenodd" clip-rule="evenodd" d="M562.168 159.724l325.95 162.727c15.062 7.519 15.298 28.898.404 36.746L465.19 582.283a82.875 82.875 0 01-75.639.83L123.74 450.409c-32.376-12.972-68.568 10.748-68.568 46.474 0 28.728 16.256 54.991 41.99 67.839l266.48 133.036c16.267-16.537 38.918-26.795 63.967-26.795 24.334 0 46.404 9.68 62.558 25.394L822.075 521.45a89.893 89.893 0 01-1.385-15.755c0-49.44 40.14-89.519 89.655-89.519S1000 456.255 1000 505.695c0 49.439-40.14 89.518-89.655 89.518-24.21 0-46.178-9.581-62.31-25.153L515.94 745.065a90.036 90.036 0 011.324 15.417c0 49.439-40.14 89.518-89.655 89.518s-89.655-40.079-89.655-89.518c0-4.572.343-9.063 1.006-13.451L68.622 612.068C26.566 591.072 0 548.153 0 501.205v-26.15c0-35.755 19.82-68.574 51.49-85.261l435.039-229.24a82.87 82.87 0 0175.639-.83zM427.609 794.912c19.044 0 34.483-15.415 34.483-34.43 0-19.016-15.439-34.431-34.483-34.431-19.044 0-34.482 15.415-34.482 34.431 0 19.015 15.438 34.43 34.482 34.43zm517.219-289.217c0 19.015-15.438 34.43-34.483 34.43-19.044 0-34.482-15.415-34.482-34.43s15.438-34.43 34.482-34.43c19.045 0 34.483 15.415 34.483 34.43z" fill="currentColor"></path></svg><div class="css-175oi2r r-1ro0kt6 r-16y2uox r-1wbh5a2 r-1qhn6m8"><div dir="auto" data-rnwinearest--1ghhsy9-hover-focus="true" data-rnwi-handle="nearest" class="css-1rynq56 r-gg6oyi r-1b43r93 r-16dba41 r-hbpseb r-1rasi3h">Powered By <span class="css-1qaijid r-b88u0q">GitBook</span></div></div></a></div></div></div></div></div></div></div></div></div></main></div></div><!--/$--></div></div></div><!--/$--></div></div></div>
        <script>
            // Rendered with GitBook 10.9.349-d20c80b850d5e98da3966a9641d3239717c050ba-5292837991
            // Space 2uNPjhKHrderJ6Wu5nbe
            
            window.__GITBOOK_WAS_SSR = true;
            window.__GITBOOK_INITIAL_PROPS__ = "㞂‖འ츂аⶁ䱀⸑ₖ〓舂퀍悔\ud988䀎⧪合݀㦮Ę䄱轡ࠀ킃晅\u0005а쁢챊ꄤმ怃暐夨⡠輙ᩌ恠슥ᴀ程ࢩ兮펷Æ႐अં➇䂺䪇̅ƌ\u000b脢耂怈⌊ᇢ苧ܒẀࣀۀǋ选쀄쀊쀌쀎쀂젨蜍ڑƕ鉐Ä廝폑ህጓ༐Р৭ ꒀۧᕐภȥ嶨뜐ఠठਧစꄲ圆倊ꂀഥ买૭㶞賀蜍者윍 㭠j䕹鈍辑ꭜꠀᔉ뭆ꢶ퀼娦쌢菻䧚\u001f〛좖卺愄ᦂ᫬ꆂ襨㠨㤅괦쇀살尻颂蜚恊휀Შ者昇㭨톴\u0014김ອ猩샘樐ᬣ鞅쎭꺰圻폢콁厔驁⒅આ훪瀟᠗쬪ٓ憘왐顏깭䊉ꊚ撦ኝ䶧룭さ㒀ମ甐\t쎊ᔪꪍ獡㪠Ჸ갷؜슉憱\udc01ᨾ猠冣ᤁ໢䲧끩\udd22瀁⠀斤왓㦊셎썅蒚嵁ᦂ腢熘ꨛᵱ迠덍\uda16㘅閃á焈罪Ḃܔ惘챔ࠌٺ䀬鹯ਊ\u0005ℨÄׂ년꩗薔⪕⪻ﷻຑﺶ휜乱呿ᔍ釬<赅䀤삊ఱ쪣㌍郾䠬裁偰㌀ϰ₴耋쪁쓘ȀƐ쁜ਇ\u0011咜䑑鑎Մ⹒ဵਈ訐ꔵ䡁鑥ᜑ䤔࠮䊃ࡥ㮏ዠຈԲ찋㋊끬㬾졳ᱧ◃燜⤋赱Иू儔舌✒쒉ᾪɨ䆁ᅁ卤鴙佐뱍ᶕ郔䔗䏓瓮齌ꆐ〉앀奃᱆㉌㌜쒰걫ᛋ뀜䜩셱岷㷈⃉〜溋䣊Є焻蓡耯࣬\ud8a0㼵쵻Ў䕈ⅸ鈴躅젊ኆᨈ팝涃疸ἢÖ亓転栈ḁ垜벼ឃ㋟㨎卌\udbcb䡻⋌ꌐ遼⅑뷬ꁌ낉쟲᳛ᯈ⨬쐟젪싡耎䳙ờ⬐芉䶲貧厎툊흶ͷధ富\ud980芈Ꭓს鈁ごꉰ咂볉덤ན艓蚰耈ꖎ㷙㡯㇬君ඣ㛊ᎇΆ䔄깍ڜ䘁䱿㊏跀峜䜫䨌Ჭ迌㳏蛊㡮틽焉왓᠊\ud800쫚⟒콊겡쑘\udca6占笲뻓擧㊲犌콺䇍뫁澆\uda18움鑔৑匶튞콭본\udca7၅괰뮰਎덤体蒁ᓄ㮇တᒌາ嗘䨃嗕ൖ仒࣑὘띈㶠钐梉뎜犅䌂氈⋄总단鿏ვ輪졟ឥ凉彗뗽磟㝽ອ箬踶൸惆Ꚇᄀ\u0000";
            window.__GITBOOK_INITIAL_STATE__ = "㞂⁦ॠ上惎Ű㶬䀮净ค〱밃퀄쀫聲(ՠր툀䥀ঌ倅‛êꐊ쀎쀑豴ꃱ​攦₄燄耏겡OⱢ킂䰺谼ࡀװ͂༬ᰈ悰ࠬ挊떛뒀䄖戜劰肳萲䐑摓䀄拠â怇态悴ᇄቂಕ༎ 掊⬯⼴뚵녠ȗ坁\u0004튐ͱ慈ܐđ䱦ؐҐԑ怂퉮␗凇ꋇꔥ梈ි耇㛈耂脌栄瀀ꂀ͓質阖譍⋀Œ樫们惙䍢蘚葠杆酀ϫ䏙䏸笝֍蘁슐6ࡊ㬊䄃臀躂䚄။䝠䆌ᘀ㖌ƣꌡ僨䱖㬛蟂ኈ㘄ꉔҘ㔢↤ףּ뇍ࢎ䔄Ⰸ≬鮛쳄ᴼⅰꠙᄂ\udad0鲠唆譈폐ᢌꙊ뢦ତꋀ艎ဂ⤚裚砐죷\u0016庉䀀်筆쬊䘑⫠䒖⯄闩퉑幮鉔܂됗稪ُ賡붾｠硯鎘2赕䈋܃䈑࢐堰鸿ك䚶　ᴖ줄苛\uda70堬獲䔤⊴誄愡ୢ专뛉Z㎴ɀ놛\uddb2혉ࡈ䈶Ἇ\u0002錐b㒚̙迲搈䐰揉遼ᝈⱺੌ行ò椬Ệ론媇蝐똈臲郉Ⱉ닁Э耇儀ព䅠“\u0003♀⥁ᔌ䑘㢟菀鈼ᩲ⣀䒚獈恏驰䥒槟蟠ม삸᠖럠㘻Ґ喚㚃ꇨ度葧ᢦᦞ摙陕鵦焤刞䝁衢ภ끞ᘆ쎱ᰥ͓焚伛쁁籿ဦࠊ琊█舡⧸䲛◈결鴃䣢劜ꌨ䱿⋆䗣Ў拀璚麤桚皋ꗩ﨡豤馦妁托嘵龌숐睍葩鄤ༀꑘඏ֡눦켱聎刞뜈∤苅쇅䚚ુꜩϒ嚋ႁ葏䒒ꑀ὏퉼㘠蜂腊晴阂ꀜ偖牀প桡⥆艦㉗鈉闡㶑⚕칩鑣\ud9c8溌錹졗臐ǝ皦舥\uda38㉜蘡䙵ӫ삊爊껚飫\ud8f3娜蚠☲䇒邚⒁퇠鲄࢞蠇嗠ĕㆇꈠ町ঋؑᠼ\ud913섄ݎ≠즉耀텡栖賦䓱섓饠砎ก쁸ⱳꄽꆦ懖䐝⊇༝ˀٔ怾螡졤䖄외縂関舧ꆕ릝䁵䘓ퟳ촆ୡ푡ᢂ솎꒏ム♻潣외ᘌ⳨㡖藜䁠䆂⑺ร␶ᘚ㌀၁貨䉠䪺궫퀢苅聺薯ᇐ熆ⅿ䨘枠砤脆ᡰ溏ԡ桎ඒӎ㬒꿏煆颸饋뺯毺游匂쀳尭䝄ၑ摂繛瀂ก ௞隽硛푄⃳\udebe吡篾깫뫡멮宥㪣틕ᜓ坰䳺\udccfᯜ몦➉騠橀ⲇ⇤ႁ㑅抾俈塼ৡ娌ߒ츐죏༅龃绹І\ud92f羋鐁ƀ긁ʊ╅쁍衉ଦ蓌쑺Ű嚍䃠ⵅﳇ䈃偨蒡졼ʞ近ꉍ检턪ᆢ䃔Ȃ㐈蘀툰蝘錕ᴀᡠఅ␠H⠥ക䒜傒襚䢥㤮锔蒂䀪䧃ဿ璃螾蠩鼆茬蘈ﹶ䮀ꐇ⊐鍱ℤሟᬃ聖ȁ怹䡜䀸툤樱ꁰ㳇놮ᤠⳑย큎蚐∜Ďꐐ놜殃桃㮆顂遹ꑨ袤䍊蓐먐슘䬋愜⮆⽢ɱ蘰茀뫂戽㎄儺ጲ易ک㑺ӌ硎¡ﰨ죨ℓ聄䖃ᄒ⩅聾ѐ쐂贈贅䐤떕钄躍諢䄩䥤ꬤ튂鉐쩕䦠戕꓂궏自驺㣓⫽屰ཱ忌Ԕ⸋疓䁩ӛҀꅩ䪉\uddc7䇄픞榮ᐁ䠼ẃࠢ走ꐪム쐂懠縈㆕ቁ⥶鷃\ud80a⪶ޔ々툌○뉀㵌棝㞧쐲䙘좙《擌쪌䃒ᖎ⁰ཡ䳡ɹẒˠ谋憤㲙⎜ၗ僦㳑Ր聈똷ꎙ簭\u0000洐୐∨쏆敝䆒二䂐᱀裑Ӳ푚谡먺訨瀙Ꮨ䞪〦㹔ड넉蹁馉샘Ჯꐌ鹚㏆擎餛ᚡ⁁谠뀵ʐ胠事䀝ᐃꙠϱບꐞո\udd0d⊼䄃鮕ꯃ쁩ྨ鸦渼.黊凋帧꣍ᩲ䒹쾊鉉⣉咯␲銗㆏∠䐥ꍢ樻졾謹ݼ霜됈摄ﻶ寄䐐庺툶좁ℾዂ칏ଅⱌࣝ놢푗訰똺螰鴔押憍퀎⯅샶עﹲ娘䀫쐰됐䄾ᐢଁ瓊탁品꤆첨䒚앜鎭橊⪒㢬閘ꙕ쪅咪窢䴂拔溁ᆦ㊴༱쑖藀쀲닂ₙ싰ꄠ吆ᆋ\udd64ꪐഢᲑ䃘撑䐜ꯜ猄뚏側ᣫ騺䱽첝丂⌔ឞᓯ苊䇏\ud9c4夵\udfe2㝝鈍걘苮봸琫॰먦㐤傒琯뉴ᰄ췸㔆รꠂ൱鄱̤꼗亇⇘ਔጨ搂ᇢ㩇죥ả둾踱엡삶⏅᠜Θᘳ殭鄧䌸숉馀㱫㏦冩©ᵂ户쓍⠙쇀֟舽亇óГ䠠ᶶ닡㲣䓆褹ቦ⥉ﴕ片熋뤓ꋅ꥕㛳츲丬쪮큙茷䚗᠗ｗ⪷숽ꢅ⒞좝朑墥⦍ᗡ‟䎦\ud94e荋ᥫ⼢᲼곲셚⬥煹⚔횚㍖槍禠딖늰樾䂊夜敥熎ꆲ琴订䡧꿬뺼謲뢞灧⑮峡푣湸퍲⁤ဇ㯔숈嬺୏⶝㞶沦怩栀뼗曚藇簦麳녺뭚㧐鴉ꄴ㎍䃊㴀鄧蓡…蜱꠱π֛ꌅ욂鷊谇쪺뤍ട몛퍦滍릿㗄䋒郸ꕅⷥ늷囚\udf5b᭴ꥭꃵ蹓逌덖䚍蜼碁鮲凚䓚㬓娳ṉ봓輌䷋ᶦ㋂⦙멏幼ჹ皠\uda7e몰屁裼ਠ馶皁蠴䅈鳸펰諹ﴧ黂闭磑ⷅ檭㖶臖蛔\udb1d₌๣ē薬伹׆撍휫爁셪Ꮈ폮ො쏱Ꮗꑗ˅艷꿳ꎐ㘱잡螹㤷৔擮왏얲뭓\udd41넣ᦝ뾂踨䝸뵙닻柍ฃ\ud852ă䐮⯹㙄⾦렴萪狗Ἃ낥䚄ꁮ螰݄謡ꅠ件ꏯǵ砡ᇳὅ⽑剀Òഴ脍バ鼊낀݆靄ᘃ왑茤♢쁚茤縂Ύ଄筨蓋沵쬈蟋䊶⬚䚕ꅺᑡ昕慶ቨ世뛣䶖\ud95f癇仔㤞퐛惶ᬭ熷율䬖노灲嵪燹崵콴㒂砟ᖿ噳հቿᡑ⼳톉㟴桇ꌤ㉇莘⬄怼憀㭕硼⤂燐⩖᠗䇠ᐃꑺ砍я囵彗Ѝ惕ദ服䪅㕳咵歕땻呵杕畻Ᏼ蝎㔑佴\ud97b則ℱ䜕ቭࢹ淵錉뀧棲✇喛ӳ꣤琖냋窡켰呈䋵烋㇧埴봁焀冀聒Ө⒂聪ňⓐ깚ɦ䘆䙫艈燠肿퐄Є屄ਰ滥꼝ب譑夲讵ݒ甗卵䗤ꃪௌ娏ꃆ๠혏悸絗ࡣ冋ሳ⍢£⨱ꌺっᰁЋǠ阓芀⒆ၥ怬嚆롴腉㎅ᡸ黵䃁凷Ὦ덨딏툛崕ே䣰匢琿ጎ㼊牏ଉ嬴漧剹褁筓㍟∽㜉罳티냃爤ꨊ쀸虖刀耶ᑺ殇亸ꡏ䞴⠃䢝߸영ꂻ؄ꘉ悶࣠엤쒭蛄\udc4f쓂两뒅⓲䲄イ᚟䚍齶勠ᰇ酕࿷嗱播୤᭎侓⦴礕㎏㔷䫹ᓲ颰冰샗켉伈縀䠢했哵讳ဃ䠄Ϙˆ䐞闼㦃筤䘐稂聨蚠ᎆ롢ƈ逄ꀂ유Ⓝ챑蒠笅絳䤀杍璼䠤ꉉ⓫茤엢꬚녠㪰欦녫㚰࣌梵鉨~㉟皏僴爏෱ྲྀ侌裴䳽嬍ᣓౝ䴲孋஧紲﹏陴ﲜ鈉斉㬏঳૏㐤ڸ⊂䡚茀愄᥁艨嚃⑻ٯ㦂昮ļ廊㨏ᝅꡁ螰ৎ峭赜華武땫皰衎뚅䗀\udc4aʄ㔑匕॒镬㞕䕖售됏㻑췇㯋\udf21蹌䳗쳌즍卵졧ಓ戂쳲⁑Ⳉ޴Ω胥晖〃챻ߠ濵\ud8ca鞰甆Ϙ━쐽蛐兗딠헢홈ᵑ됒\uddf4ᣃলㄨ崶㊧矎ᒋദ衱䱰쿎 儬겅遆芃䳤ဂŴ犓饨슐ᝃ袄詈뀁䢸⁂磢䁇ꛦ␁쁙搬拀䁒윬䫆갞⎬幄氖썬ໂ쎀ⷀᰡ서㇀鰩얜秇뢕싀㗀\udc26꧜㷆帣씼珃ꐫ쑤淡摻씼ជ쩼ꮀ߇㈴藼ḅ格ĸ梇ۆᎂ䡫蟿߄誚Ꚋ馪⠸꫘Ү㰢莈䢔썊쪤⅂Ї䈁⇂㰣達◾㨢嚜ᢄ䑚⟩縆鰜É⊄ꈖǉ攳쀰É䜡⨐薰礅砥티絔⁸⋗噒譵Ⳓ틨蟒툄㋣Ⲡ匯萔ᐐˢቇꂀᘆ樴݃ᢀ뀢䙔啃刑午桕硾ʀᏂ耔⫠冀莀冃쀰嵖灳⻐⒄▲飏늰ﴎ퍲쓷ク⼿榍껛㿏崶৲᥈덬귊ﲯ찢쇐ዃⰊ슬栀ꪠ芪ﵕ汶쓬᠆쟬䇆᱑윜Є鰤Ɯ㧀尥쇪뺬\udc40緁帇쌚쯀摎ʚ므簹ꯊ낀籇ꒄ⸂䀿沠☗썈Ꮓ쀹肀筣頨⓪ᛁ웤⍂ఢ쉜₎﹢蟠ฦ⁩삈䋷긐䘡쀜Ԟ⠔蘠᠆瓁牰꧐ວ䙺遚靆ꐔ욦웆첮磿퀖ꅩᚱ溆䥮雛֖ꚺ橐٪曚ђ鳡\u000e楔✄㭨匸䆂⡸橨⫫왍ꤼ㠄䋁蜠⊆耳⿘䕮嚿ꯏ⧟ƈ゘嵯ᢡ䰶餭♹䂯嵼⭭छ澚芨盷⪷涬ཨ氯涪\udf6f갎隩໶ꢎ캮軥앜㩗軭쑎嫑꽞熯些욚癜ﻲ昳蛵⒆䑥懀䘇ꁮ蚠䘄舖褐滵萡溷꭮쾬☠ᘁ蠢剈⒅ꉨ茀ࢅꈫᘀ洁㰁䠧芢ѫ⠍茊廏䔱\udc6f졔桀巯災䏭웻넀忯ﺰЁ밆Ǉ匁횀膨᬴遚淄穬曦氻癩聎櫾뼤ꠦ朠⠄ʣ媇뀰ԘⰇ‼捈㱤\uda23ꆁ謩눥澲涴䇮趌鐜횮䩌ꔲ솁俖돶첵뗲뢇봴㭐귰眃頠葥㫅説Ⓔ\udf02䫪倬ⱄ\udc1c櫊鲬ꇻ横銩盲걡贈䀖᧶直໭싡뚫ຎꪎᇵ옑臅ᆃ쑑퓬\ude49깤Ⳮ髹ᡚ蟃왱쇠Ⰲ䠳艈♠䀦聀媅㰠㇠䨁䠇쟙뎬ᠺ욺讪뫢薺맄ٺ竌⊱ﰥ䉕ᅈᤒर滆⼝ꉺ⇀优蠖ڜ᠇荈㒃ꌉଆ覝꤂욛鸾蚚榖鯌㚘駩뺞騩뤀继ɾᔟ骙뉥㗦余ۘᙕ⩵烎᪤䁱讞摀幊腉⹓௥Ḗݚ氖Ȗ桎萘ᔛ聻肀㱧끐葠愃찓옐㠂䠦蜚憯敉᭎귥藖䑪䦥ꥨ䤀稀꺴萘䩄᠓蔘ᢂ遑薍ꆔꤍ蘐憁惖肘ˇ倈菀㎀聗薠粣顊˘㱅浊艎ꈂ薉꣎䧵൞ᯓ봇퉽៓紜ýᰂﴬǽ昷\ude73ᜈဆꁟ숅䆀ⱟ쇴殀黟샠݂晨胠亇ೱ鳟ᯌ犴Ỗ릝䲹뛁荮姿鋝䇩\udd22᫙툘ꡨ嗡癓䌌㝢\ud954㒑଄鰖ʤ巉퀿䏐ໝ‰̀瘅圈ް㒀琺ͦḀ顚:摁ꏎ芖Ꭶ㒓ꏆ䞢虲Ӻⅶ‴攘䞡㩡蟚媅类ͬᝎ舨忄材ঁ蕆樆䑪ں帽ﰛꅚ䀘⍗蚸䨏蘷ꛨᾢ桪π敥꠩Մ⚇挸ᎃ耔⤸䀥ᎉ芐݄䘂嘆圽䘩Θb๸揘㉃\ud85dꄼ䡦ꁐ뼣쮢ꃲ׍亂泐⒳榭虖㒰ꔆ㑠琽蜣酷멚Ӻ溅ꁚʓ褾顫蚠⨋⑇ꜣ쇘顨旍ަ嘑㩀㇉靼⤣뵣頫ꁺ⮡였懋聡㧠憃薠硥砭艈画쁢抐ౢ格옘䘆頙兠了䐐⽡╻Ȩ履胸履⏀柺㡠琳藚憃蒶⤁㰲䀺䌪礼롴娆᠎πᅥ奔旺♢䵤뵋턼ؓ슐喭폀揳ቦ뮴揆㎇ꮭ蒓鸃챂묛\udc66⮦菘樹珡虫뛅胻ް۝镮芳봆洺Ѓ옱肈嚁树䈶憁㡲ް␀温ǅⶌỡ苿牢逼悀ܰ姠๦᠈f霹查昘⸆ᡎ思鞿倿拘戃찑\ud938ḄၲļѤ膉菳䄄Т葺笆嘤ζ仂遞挸㠆ꓛ钽ꡊ材幣顋積敤᠈⒕戅ᷡǠᏂꎖ퀸ḃ衒ν冇堟媋㗟뵇홽埗絏훽ඇ\ude02縁à㢄ꁫ臠敦䐴蚦嚄怂씘心쑊腀ᶆ͙䔩숇㡋膸㮀砧腸瞄螹寧኏⢘驶Ϻ矁풁❍鷏抂黃틒₇■蛔ⴄၫ窩Ȇꑐ揔䐔䁀㳂䀿튰㽭끾≕콆\udfcbﶦೃ䱨݂谘쎌ӂ䱶Ռš됥풩᱄ၸן鸴蚎\udf2b苜Ỡ輆砛쀾װᾃ덗 ԉ譑鿭㡏 ﾚ懵Փ粩⠞꣞д鐈쵆臑䄀嵔요ǔസ䤃ꘞɝ∁퐅푨凤⁋ꆀ\u0000ᵁºᾁȌၐ莄ဠ퀧郈ʐ㓡ഋ‚ܟ씀ᐊ喕ͧǌ᪙ꀅ퀀أ쀋t蘀⸀\u001b鞁戌渴ꆤᄨ᠁젮膊ಚ㔃吙ﵵѨ✀焇礼ࡠ섃ᠢ䇒̰䵉Ⱀꂅ쉐㪁䪇끦芸ݡ䈹ꐝ솞ര䲂Ⱋ䃿ٲु퐍禃荬◀溃琖ꁑ༐䱃찗͘㥁㩁䰪䉈芐㢂䐨섹ಐ侃搟ႂ萄⤡뎆⡙“ᖶ㱉瀀셕र䵃戟郂蛘Ⳡⴈ灄䁰౐戃ࠝ섢ຘ䂂䰋삙萈⥲与蠌Ǫ蘀━➌(탘ᛃ\ud81b焢㡘ᝡࠁ㰯脽ຠ爂ꂡ휎賡⁩서ㅸ툦鴧䊁䆰ꗒ젌젡㒸亀嘪幣臊씚딡댥䂳웁ᰀ聉䒠޵骈鞣똕ୠ栃ᔁᛀ熘聺ࡗ⏁\ude14艏藂㄁㨀\u0012施ᢚ㳎蚄՜⭠硦䠁꠆ಶ䍐㰡ǅੀށ搓큫얤Ⅼ慣뱈騡ạꡆ㰣貥憐\uda83愓屈Ղ⸑찚葋䀟텸︳쀗Ǹང洃䈣軸䈢က쵢ꮰഀ砄䌹⎁Ტ癅␹䁁䑵늀줙偘⡂輀紦聡ᗰ렄鄕連\ud810ْꌁ飑좃̨䄠촆乀栎ೠ愴案㢇ေ密⼑愶푇ꎌ辨\udb01䀍8蜿騢⤖᠈섿컢⿷谚ϟⰆ吘噙ᒬ錒퐔쟂㷀讄鰖襳ᙨ适⢘ႋ웙✬픗愺쓨ॐ舄Š¼ୋ惍솀㫃ᶫ䍒ꨐЪᩃ龊䃜报砂툿홬ᇁࠀ?坪ꥈ㪭嚸䀬몣ᵠ寵䄺첎亄豹ᴋ䗛脈௠\udf01샾῰聆Ȩᇀ褄参딑隯噥뭴뺠䐢ₑಈᑂꈍშ胄☠ꐅ衬䆜朑뢋쑮쓠ࢠ셑䠮͝ᒺ⇄踬熍\\ڹ玥㣘ˎ⚆伴값⁞㗄䓑ꪧ軜滢༞룕얉釗㱀赺ꐣƫ苖耭菢摧ଓ샧儖Ꞁ⺞삋ꉝ㋨坊먵펮놌≬Ӗ䎺沶䅻ꂐἛ愶裞䔞꜐➭㡹乺⤀府⏣ྈ╙㘛Ƭউ붴蒊䐉蒊鄐䨅ꀼʉሀ䱁ᘥĥ轀嚁쬐ⱍ쓜❱䠃픸ꇼ體皢㝙쥷ి賢蒉쬴色쨠㔴⎁๨炘潅嘞Қ፡촄엑╱豍劤劧ഔﷆḨ聜䮤弌腯쒐娉⛱⍑ች渤턁죒蚊㖒粒瀊嵖莗劺헕꺜쇫ꠄ웨椢왚伂樑璟꓾䣉⏓ẹ錬鬽秫ࠑ竼䌸ᅢ鐎룁駀\udca1࠴킒ദ憭㴈쳁埽飅⥣榤⅊栀뚉摘Ń峨㳎焴䵶赡⪬쌦썻亪绐檀푚閸鸧㨂亼泭Ⅺ⓾ꙧ偩᩾甋걝熦⤺椪䮚媒誖挐♘\udb49巗鋻ꡤ餷榓횞臒沔瓂䓼 譎⩊勢惤Ὀŗ放낵栊⵱楟䙚룔숱䶍樀単뽜ᑥҵꟵ徢ታ̚贙\udc88\ude26㊗枼᠁眐뀞᧱螉簱塐䄆鶠䅏殱㊝ᆕ䌀ʠ杨鄶Ṩ꠿뒔ු헣三᠕瓨㊁Ѝ䁺Ŭᚠࠅ栔脄ܘข퀐耄薰⧍ꉍ㠜㨕ࡈ૖츅\ud964ƪ峤娆쀹䰵ʄ㣂聴ɺ\ud910销๡-甂퐆풭ը⿡䠃顸Ϙ઺䔦乶鮈೧㦗䰮珰஖耷ҹ旌尙ꓐ՜髧欤Ͷ㊱ꠍ灎耠௄ࠏ―浚ඈ嗠Ꜧý줈⃲આ䡬푹⠧Ṥ铅᧤圾秳쑞墍ࠍ㠾\ud920༘뿄뀩蝠䓤套橳ꌎ鳌⑹Ꮛ침䕈Ӡ㯥簷⦍蠹ၑઁ\udb21꣔펴繜酠嫧縏ᠿ슐༁鄈쀎샠᪀最琴뵿Ҁ݂肸易⠞搋⾔㌘ᜧ雹빶૖乜바뼠藚좀㩈줈なŠᡞ؆┯끠ੀ῱ꐉ蔧죰嬋ꁖﴱ낹又繿୧饜ꄔ耖륺ø㔀堉ꤨȌᚠ䫆㲷䃠࡟凁ἥ䕧츞粴꾙싍ᐠꞅ䠭⹞誟龂ꌗ欨㧂ǩᛁ师༘괁㠲膺ތʑ䀙䔬ⴾ媊\udc51슍ᓟ⭅鰩텟਴䀢茕竕蘿띾䅠丏⊞ĳᇨꐀ琼Ʈӌ甀⒠㉊Ԋꋌឰ뭀餯칶䬐崼뼖ࢨꗂ⭾悁ẉ쬪捴ठ刂耷䅿ʄ⿂㴈【ͩ䐋㩞ꋘᝰꢹ㸭셡䮫鈲銔鸄⋶䟠⌁\ude08Ⰸ舌ᑠ塍ࠨ쀋લ혗경◝ⳙ彋뱐㋼韨맹쌬ज़ୀᬦ됊鑅ʐᧁ閏쁝ꏜੀꐄᠫ䀞媒Ꞗ思씽⮁型뙑żꀥ뗊䊳ゐʐ绲珘င醦₀봤銧ᒤꎥ嚊\udc96ⰱ浲莓쀼ý쎀펂䀝ᅂ௸⠁㐀ꐆ²䅸㏈幖⏂몕긪䕆䭞僊\ude15㊳ᔬ꧹嬪ᴀ䜤눌ᦘꐁò栠垃톂镽쪥䮊끛⪗镰귥텳⪆徲\udf94钧찤세㽉젇聲¤ঠ本᠒섄ѐ憁䪬햴꣱噊ᕓ닁闬뢥⯃澥H엌甃訊┳ꋺ⌁㴁ਠ햤ꋕ璭䕶謕宲㪭锅耪ᐁ깕،ᔮ椄态磽쑗ⴙᗲꯍ䑪᪃铆꠹휇ꀠ耬꽀ᎀ瀉⁧ᑠݐ଀끻陒붥솨\ud955ꯃ冊芖ᚺ㕄Ȏ䧠鉌찮\udf80쫃耣큗防݃ꠁ딴궝枋子몬嚲뭙ጤ稶Rಈ⤂㴙탈荑茅鄆決̞ꙕ䶫镜孪\udab9疁존Ӏ㠌蠮\u0016଀嬅ﰞ쇔π⸀䀉颿苙㤀뽞檟홚공㤯쵤檗姚ꈁ冑聥ļܑẏ갨ᡠ␔䇐툚鑕沱閠߲擑贛鐴㤼냔ꀂꤲ⃦ࠠ。諔䪤䴢\ud8df锖쇀ऀ䧀«ʑ嗠\n配厏鱋듄픴ष㘊䴲橤挢ꛕ㒃ⶀᵁ尦高ඦ䵥䀳䪛뫂裞珬㨰輕脋ꇸ橀⌀먄촱䢰ं琄桑ģ鯑贇뀹驙䋸颐唹㜆篍↚쌯顰쟦쇓轢싚酸躥帤䙒걑뢚\ud80c슞ᵀᔋ耉쁳䙈棁ቖ䃬፺ᰁ脭㐉『૰\udd8aꂕ㨂‐ؠැ뽅఼懖轠봡㠞쇨\uda7a냗ﺯ▀棭措损퐜妍뚘瀂\ud802xැ಑ꬉ⃔ǀӛ鹓骦㛡붵魊⠁⮗몆У阀쀌ꁟ색쁰厫奉\uda1a練䶩喋곫寲莕뀼쀒龤ꌀ䀄䂠ޘ㱢【䁘Ҡ⏫髏뛦꜍涭魩\udb6b魐㮠䏃胑t㰊က塐ᧀੀ퐃\ud986쎷媱锅꯻䥊齅뀼Ȍಐ椄ꀙ⇁僅瘊퐂稺삧乲釔皟ᒱꮙ倁刐駔䚒鎊|栓傚⫍ᛊ슋롱⒀᪡鮺쒠뉃ﴧ⨊捠␋䠖⺒䁶쥰䍁䩟씻䠖묂〪䊸㪉⋙䢅쒼츭핒虛ൡ駃咷焣⵼䮎靓廚匇쌫뱝蕭籨풚ಈᲫ䜮⁒ѠΠ耎ŀኀ簅砨笄ೖ쬚頖\ud9c2扚ﶥ遤䈦꧰而靻婎흎飕첉 ꢘ∄퀲᝕ᩮ煳䵟㮛基鑴庥啅ꫫ䢜偑舰ठࣕ栭䅫⣴ⶀ䰄ݯ濫냟튀㛽ꫵｬﮔŪրདྷ퀚袔φ㗁萂㬴舫칽塪魗窗\ud97a핔袶豅ˀᨽႥ\u0003ᤉ헠뾆ꍥᡏ핎倫徧뷀潾䎠툃遷䆹艠鴁瘴菀樃倌¢꼨枈쀏몝読콻至\udd90ᐣឺ娘⽻楲\udad1횕꠹椇†腫笃䐞샔֨᱀ꀅ쁥扝ᨠ뀟ᕂڐ㣆鐎ꎹ絗奀ꚇ睸榀ᆽ堃봽öૐ攀灥뗧伇篟썜ఀ⫇꘸휀心꼨ꃍꊐ쁺ᅞ癰毽爜뽂虊彏㦃速胑ɨ㹕Ẍ볆̠ᒝꐃ옢ߴ㴪谷쏟涧儆损벞ƀᇨ좁씭䃘⨰髠䰛刜թ䞆村່柭昝｜䆵⸀ꂵƀጱ껄㻥愳ୠ괁䠴蜻\ud8be씣းĠ朚M睫낸昣흦௫ᔀ䯹⎝຦熀맏⤘酒쳦숇個ꄞ脘鵐먒䁬ܘ줡ጀꅫꛚ⺀␶Ýꄆ嬂鴻촳蠤ड䩬\ud836䉶薖Ꜳ逯敪姑\uda8c䆄卤ⓣ膕䣧田\ude2d㕔歷㎾法⽶따ᚙ毷痢㰸ꌇ奴紽྄먖쏨൰奦倖聱@ᔨ劃⽴ꏪ\ud9ef〚ڮᛱ찍ឳ쀸ᾨ恴亯嚣퓅ꀗ聴줮퀂㦬벝ќ⏐崎ꨪ醺ғꕇⓘᣟĀ㤀암挮茪ཐႀ짳ᅀא혇]܀彀鞔䃞歶醀诒Ȯᄪ貞ᓳ䵱攸漴ᔝ醵❩懆ﳙ\uda4b朗粓骔춄䡋沂䠈掞蕤᷐盅맣껨샇멒퉸ᦝ俸즫\uda58খ䶒激₝㰲낸࠰澁䠗䩹舨᳀ଂ㺙ለठ猆‒➛ꥌ鑍떠茕턁ሧ%㠖௒猃讄냰ສ툃㗋åᡟ篋뿔ڂ㘇╘쌂栯瓳ʐ䞡瀘噜ϝ庂‌、줠﹖鴴䅫㙾쪌ꑧ﵍鰠ᜀ뀌〱宎첒﯎နÎΧ♣媅旱ᫍ攻進懩츶泭⁨䁎ࣀ笀䰉¯҇赱功ぎ毭줛ވヨ梁錂푍ܠ⣁閅끍ᝒ쨂㥳픹럏顦㖿聴⃀쀆䡡臣ր\udd05뽒䁰Ґ溁职옄㠗ם\udee3춪벀怆ᠽ膧ݖ䥡怕倌ὐጰ砃맿䶽믵\ude19郤ᜈ㻹껔㨚ȝ鱀☀ɠ者鐸ఠ熶떬墨ﵧ䰳㦓췿몀\udf71㘽ǐ똒淖肌ˠ㶁쇂ⷍ뚹굠蠲ⲕ㫰ˀ 㛔嬤ু꫏䁆ᝉ烃ﮚ䣻ᝳ㧅쬩`㝁ㅉꬽ䬨č堄᠁霏㔅\udff4⯖顳Ōడ郙ᰛ茈ᖠ坼㇅ဎマ㝀ℐ銳脳၀큆ꬋǜ㓅잔륶䭵馵䊖袵훋颡䋞ꋴ쩘ॵᏃ⠙壩嵼翔Ჹ舶堣讜䘊ℨວ䞢癑肽彲\uda3b⯗㬫舌ր䴆㊱烁\ud886袃痓\ude35鹲쬖㯛喚矵癳䇋찴䀐ਰᨍ鉰惑 р줉䱢ƥ潫帘㫤둹欨ꃈ莈ề릊캯췌鳫瀂昧䀋π䏦啠쏻徟篖睫㰢䶇տ쒀䘃尋怔Ⳋ婀얰ᝎ꽳㕟蛑혼떕逵끅ݩ㪀万頼솀Ԡ灭\ude66镦뇵좮칾삿蘐ḁ缋ౡŰ฀茆嘺ﲼ搵\udbcc獡᭄餀؇௝臒벽쳳构ୀข븗﫶ޠ㈡ꀹ腖素꼆雹㝕맥헡䀟胪鍂띀쀋倎+퇨ࠀ綘⢓ឬㆭ讜\ude3a튖‘相ྠ䜬튷䄉\udc05㐌\udbc7梶ࠅ\udb08ᑠ✁겄䀡縁㌑ᡐ榎刻㦨靷鵀⻛찃৙׃衫悃̊ힷ⛒惡꿈矽ౖ辕턺௸㰀ᴓ緞ꛨ㹆똋㻺柛ࣚ隃鄃槀鱙䁙⑗㪁᠅ج஀秚㋒㛟鋀䄂躼哙猢թ樍夹芽ǀꯚ抬뚏锴⣙׸ᬞ欂杫臣Ⴓ㠴䆶௷ᖓ긋悧\udfaaퟗᐿ솜ᦦ书㎏\"ӟㆇ鎨筆ᤞ醴鮲疂샀Ӱ鴃\u001c쁸ѐ᣹ꐇ첔΀㼀낼㠘ẹ渇뇘䇒阋Đڱ쯑쇘ダ厁뙷䊛梇ꓜ滯똩뀵蝀㵬롭ڠ⭁蘄㠨褠ඦ⭵ﻔ뭘\ude16\udc0f贲悚旜⛅睒㞪景捤骬\udb26쒚㵖г笴퓙堍㖨멫鍾鬒枣鄴⸧춪㫓些곖換㑘ﻍ쿣Ⲍ䦜\udd02ࠁ릣쵞槳凇ᨉ滠뙝阢鈻욬猖끤멣콡鰲븰貟瓺笭悵쭒헂\uda19鏀閩哥栫镚煃Z뛾ậꙦ鉙檉믯欳᠂관\ude52ĤẀꮔ怶죉أ\ud96f쭫̸驖\ude06営䏚淴\udb5cွ脆\u001d쇙鈖胶Ԙఁ䘆⎪麌뚀쐀鎂뀟佀普퀌賉뇀㊰꒽ාཻ湋ꏛ樦ૄ樁㌚耼Ϛ钚㠤菘܀姙쾵鞘ۓ퀕Өˠ☌ぱ傧뺀祒䇛츸笹뀁또쀨媞鱀嶅ረ鎨술鴇ל睿퓡酸쀎患ϭ炀㠄퀖痦၀묜䃑砳꺴솢Íꛈ㊁ꓦf\udafeᥘꗓ⣋ໞ뛃펜䋩䮣Ǣꭎ樶쫐ᨊ态西P롍፦䬜뢂﬏텻㦊Ǡβ鴇媰胉૙摀怙ତᅀ쮸湲︇ך勎\u0005긬ঀ䐃胕᳀怌갔芼Āヂ狡츒㬃鎟ㆥԺ۩䯕⎛뗏ꀽ腞࠰䈰èꔳ뻍栏쁖࠺ᢀᒹ෶늉摽要왠蹴ᡡ惁끪韏男詝깲놺൰ᎂ桤蚦თꠄ遠쎔螫蚽㽱꽈皛헴ꃃϐ礁萉䀤Ψ᥀ꑲ\ud801贡뉛蚮꾿聧Š㠁H皴ẋ儤腔䤻￬钬後☂遺˔঄ዀ臧䁜曋鍶圄塬훮损裡胰Ā妢ࣀ懵Ñň銋孹ﺌ꽲虱쀘Ň地ᐪ됚乍Έሀ䀰≴껥ৈĩ㴮\ud977주燆ꉑ톎ꎦ䝨⩯퇈㏰ﬞ棯灎㷑≹堛ῥ뵇꘾嶭῕\udae3ﾇ룻種榁̨籰耝豵ῇŨ砕먟딝\udc7c㩸\udbcd崹觷乼珓褹멑鎖聏ꓭ䞙㻉\ud95a⫟鎚뚐ອ൬譲☪継ꖜ钺₯ЖỀ䶎騹莁ꛃ堁₰ᆑ঻繬ꁽ䜢궽㡗ಐ➅ᜧ鸖못　΂ͮ婁ಧu庌滨ꐁﻀḏ㐇蕟轢壋\udb80㴀퀕₀\ud880휄ꀥŶ땻饝᫮圲񠾯ᖸᯨ䬆䄨Ⱉ쇨ʝﬃ∝㬠䕨න퐌떧厅ꔫ㠞쁘ࣴ梁⫁큳Ƅ쎷Hಶ학뷡雯痧飔\udae5푭⣀馂硁¤ঘ쫂쀁琠Ǔ륾垔뭾䞪沽茈ୠ㪯Ć௸䘀䐌洓؛ￚ橎춰埂⤀頠胳Ҍᘀ鰗꥛\udb73垓岵㵩㠹퓢X䨀鸅聻ؠᭁⒻ偋禥꽞꯭㗌諭꼏짌홟殟恖菐瀻鲲３먀燙࿾䪧쁯꾴ힺ绝ᰄ胰쁜朰喻琝䀰y閂뀞繓૞Ꟁ뽩긬Ů㺭ׅ퍀툄퀰í䛬栌ﵕ\ude48琮몼ꯧꟼｃ藹\udb92锤ᔻ쌆䀴䘁垀熁坋聤蒠㜿췵\udf23ᔌ쏎꿞⦔㍞᩹肘㶁޲俣鸝甃⡾揍㾐密뤟쮷༆㹑飲掇ᵨ瑺㍨驔灟꨼\ud9a9醖㩑팟싘忪㾘๮ʓ驸泥\udc53춂篱솦ɶ➠鵚搀慪鏘乤ﮟ뤾筁ⶊ磸롪꟯乞㐖荒폩ﮧ튶괸ګ慏購叓㴵ꌳ숪✉㊇적氉囩流晾ꎅ盧⿾氕ﺕ怵痄럳輠匌㻰怏䦴驠悺ࣸ㗾ㆀ崯\udfa8鹁楡䲨෾䖩㾳꛲磄鳾ꖦꞲ丫﫮ڿꤚ뀄鎿Č薰໮뺁ఉ䀣­鮞ꥎ⽒鿪횎稨礂敱귾贙ⱬ톮먼䎴檽െ甛ꇢ溣䁦曣ꍀ쌚╃즄웻᠊挱茨愈ⱡ쁊왫᣶଀⛆賂0ᣑ∵䈧薠✲\udc61➈\u0017ᥴ欩뱔븃䧠聈㉓⫱걎䩻쿦隙쬯ꇎ肙쀦习鯁鞀킚쉯়삈骞٧觾쭈姬힔⢜ӷ↜ကⰃẔÓꎎ겈໮⯠袋Ǽѡ趴將쁥웙؈Ꭰめ㿺⁋ꂒٌ挠猨猛訌즊惍᪬歍ઁ瘀먅놯纻ᥨၱ꺁㜛領恱腗᪘ᩱ薁軪䓮ĳ律 䉎᠅⿥隶ũ㨁⇠垁笃艫胾ׂ楀Ȧ轁퀔쬖窖箼踀뾃䐂耂曄ǝް⢾摱Ǝ䀌篇桘᫲部쉫宵䰕ࡃٰⴀ관遺ۖﯺ鶾ﴸ㯬ᾌ櫪.俔฀郪ఇ鞰\udb76掀ੀ黚⟠\udda2㸩ﯹⅽ뽠럺䐕ᪿ遀\u0000";
            window.__GITBOOK_INITIAL_RENDER__ = true;
            window.__GITBOOK_LAZY_MODULES__ = [];
        </script>
        
                
    </body>
</html>