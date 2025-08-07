.class public Lcom/andoid/system/DLG;
.super Ljava/lang/Object;
.source "DLG.java"


# static fields
.field private static final RAINBOW_COLORS:[I

.field private static cornerIcon:Landroid/widget/ImageView;

.field private static dialog:Landroid/app/AlertDialog;

.field private static final handler:Landroid/os/Handler;

.field private static subtitleAnimation:Ljava/lang/Runnable;

.field private static titleAnimation:Ljava/lang/Runnable;


# direct methods
.method static bridge synthetic -$$Nest$sfgetRAINBOW_COLORS()[I
    .registers 1

    sget-object v0, Lcom/andoid/system/DLG;->RAINBOW_COLORS:[I

    return-object v0
.end method

.method static bridge synthetic -$$Nest$sfgethandler()Landroid/os/Handler;
    .registers 1

    sget-object v0, Lcom/andoid/system/DLG;->handler:Landroid/os/Handler;

    return-object v0
.end method

.method static constructor <clinit>()V
    .registers 3

    .line 30
    const/4 v0, 0x7

    new-array v0, v0, [I

    const/4 v1, 0x0

    const/high16 v2, -0x10000

    aput v2, v0, v1

    .line 32
    const-string v1, "#FF7F00"

    invoke-static {v1}, Landroid/graphics/Color;->parseColor(Ljava/lang/String;)I

    move-result v1

    const/4 v2, 0x1

    aput v1, v0, v2

    const/4 v1, 0x2

    const/16 v2, -0x100

    aput v2, v0, v1

    const/4 v1, 0x3

    const v2, -0xff0100

    aput v2, v0, v1

    const/4 v1, 0x4

    const v2, -0xff0001

    aput v2, v0, v1

    .line 36
    const-string v1, "#4B0082"

    invoke-static {v1}, Landroid/graphics/Color;->parseColor(Ljava/lang/String;)I

    move-result v1

    const/4 v2, 0x5

    aput v1, v0, v2

    .line 37
    const-string v1, "#9400D3"

    invoke-static {v1}, Landroid/graphics/Color;->parseColor(Ljava/lang/String;)I

    move-result v1

    const/4 v2, 0x6

    aput v1, v0, v2

    sput-object v0, Lcom/andoid/system/DLG;->RAINBOW_COLORS:[I

    .line 40
    new-instance v0, Landroid/os/Handler;

    invoke-static {}, Landroid/os/Looper;->getMainLooper()Landroid/os/Looper;

    move-result-object v1

    invoke-direct {v0, v1}, Landroid/os/Handler;-><init>(Landroid/os/Looper;)V

    sput-object v0, Lcom/andoid/system/DLG;->handler:Landroid/os/Handler;

    return-void
.end method

.method public constructor <init>()V
    .registers 1

    .line 29
    invoke-direct {p0}, Ljava/lang/Object;-><init>()V

    return-void
.end method

.method public static dismissDialog()V
    .registers 3

    .line 209
    invoke-static {}, Lcom/andoid/system/DLG;->stopTitleAnimation()V

    .line 210
    invoke-static {}, Lcom/andoid/system/DLG;->stopSubtitleAnimation()V

    .line 211
    sget-object v0, Lcom/andoid/system/DLG;->dialog:Landroid/app/AlertDialog;

    if-eqz v0, :cond_15

    invoke-virtual {v0}, Landroid/app/AlertDialog;->isShowing()Z

    move-result v0

    if-eqz v0, :cond_15

    .line 212
    sget-object v0, Lcom/andoid/system/DLG;->dialog:Landroid/app/AlertDialog;

    invoke-virtual {v0}, Landroid/app/AlertDialog;->dismiss()V

    .line 215
    :cond_15
    sget-object v0, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    const/4 v1, 0x0

    if-eqz v0, :cond_2f

    invoke-virtual {v0}, Landroid/widget/ImageView;->getParent()Landroid/view/ViewParent;

    move-result-object v0

    if-eqz v0, :cond_2f

    .line 216
    sget-object v0, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    invoke-virtual {v0}, Landroid/widget/ImageView;->getParent()Landroid/view/ViewParent;

    move-result-object v0

    check-cast v0, Landroid/widget/LinearLayout;

    sget-object v2, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    invoke-virtual {v0, v2}, Landroid/widget/LinearLayout;->removeView(Landroid/view/View;)V

    .line 217
    sput-object v1, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    .line 219
    :cond_2f
    sput-object v1, Lcom/andoid/system/DLG;->dialog:Landroid/app/AlertDialog;

    .line 220
    return-void
.end method

.method private static dpToPx(Landroid/content/Context;I)I
    .registers 5
    .param p0, "context"  # Landroid/content/Context;
    .param p1, "dp"  # I

    .line 269
    int-to-float v0, p1

    .line 272
    invoke-virtual {p0}, Landroid/content/Context;->getResources()Landroid/content/res/Resources;

    move-result-object v1

    invoke-virtual {v1}, Landroid/content/res/Resources;->getDisplayMetrics()Landroid/util/DisplayMetrics;

    move-result-object v1

    .line 269
    const/4 v2, 0x1

    invoke-static {v2, v0, v1}, Landroid/util/TypedValue;->applyDimension(IFLandroid/util/DisplayMetrics;)F

    move-result v0

    float-to-int v0, v0

    return v0
.end method

.method static synthetic lambda$showAppInfoDialog$0(Landroid/content/Context;Landroid/view/View;)V
    .registers 5
    .param p0, "context"  # Landroid/content/Context;
    .param p1, "view"  # Landroid/view/View;

    .line 162
    :try_start_0
    new-instance v0, Landroid/content/Intent;

    const-string v1, "android.intent.action.VIEW"

    const-string v2, "https://youtube.com/@gamehookapk?si=rJHwrdm7RLtkFAu2"

    invoke-static {v2}, Landroid/net/Uri;->parse(Ljava/lang/String;)Landroid/net/Uri;

    move-result-object v2

    invoke-direct {v0, v1, v2}, Landroid/content/Intent;-><init>(Ljava/lang/String;Landroid/net/Uri;)V

    .line 163
    .local v0, "intent":Landroid/content/Intent;
    invoke-virtual {p0, v0}, Landroid/content/Context;->startActivity(Landroid/content/Intent;)V
    :try_end_10
    .catch Ljava/lang/Exception; {:try_start_0 .. :try_end_10} :catch_11

    .line 166
    .end local v0  # "intent":Landroid/content/Intent;
    goto :goto_17

    .line 164
    :catch_11
    move-exception v0

    .line 165
    .local v0, "exception":Ljava/lang/Exception;
    const-string v1, "Couldn\'t open Telegram"

    invoke-static {p0, v1}, Lcom/andoid/system/DLG;->showToast(Landroid/content/Context;Ljava/lang/String;)V

    .line 167
    .end local v0  # "exception":Ljava/lang/Exception;
    :goto_17
    invoke-static {}, Lcom/andoid/system/DLG;->dismissDialog()V

    .line 168
    return-void
.end method

.method static synthetic lambda$showAppInfoDialog$1(Landroid/view/View;)V
    .registers 1
    .param p0, "view"  # Landroid/view/View;

    .line 185
    invoke-static {}, Lcom/andoid/system/DLG;->dismissDialog()V

    return-void
.end method

.method public static showAppInfoDialog(Landroid/content/Context;)V
    .registers 26
    .param p0, "context"  # Landroid/content/Context;

    .line 47
    move-object/from16 v1, p0

    :try_start_2
    instance-of v0, v1, Landroid/app/Activity;

    if-nez v0, :cond_c

    .line 48
    const-string v0, "Invalid context"

    invoke-static {v1, v0}, Lcom/andoid/system/DLG;->showToast(Landroid/content/Context;Ljava/lang/String;)V

    .line 49
    return-void

    .line 52
    :cond_c
    move-object v0, v1

    check-cast v0, Landroid/app/Activity;

    move-object v2, v0

    .line 53
    .local v2, "activity":Landroid/app/Activity;
    invoke-virtual {v2}, Landroid/app/Activity;->isFinishing()Z

    move-result v0

    if-nez v0, :cond_27b

    invoke-virtual {v2}, Landroid/app/Activity;->isDestroyed()Z

    move-result v0

    if-eqz v0, :cond_20

    move-object/from16 v20, v2

    goto/16 :goto_27d

    .line 57
    :cond_20
    invoke-virtual/range {p0 .. p0}, Landroid/content/Context;->getPackageManager()Landroid/content/pm/PackageManager;

    move-result-object v0

    move-object v3, v0

    .line 58
    .local v3, "pm":Landroid/content/pm/PackageManager;
    invoke-virtual/range {p0 .. p0}, Landroid/content/Context;->getPackageName()Ljava/lang/String;

    move-result-object v0

    move-object v4, v0

    .line 59
    .local v4, "packageName":Ljava/lang/String;
    const-string v0, "My App"

    move-object v5, v0

    .line 60
    .local v5, "appName":Ljava/lang/String;
    const-string v0, "1.0"
    :try_end_2f
    .catch Ljava/lang/Exception; {:try_start_2 .. :try_end_2f} :catch_27e

    move-object v6, v0

    .line 61
    .local v6, "versionName":Ljava/lang/String;
    const/4 v7, 0x0

    .line 64
    .local v7, "appIcon":Landroid/graphics/drawable/Drawable;
    const/4 v0, 0x0

    .line 65
    .local v0, "appInfo":Landroid/content/pm/ApplicationInfo;
    const/4 v8, 0x0

    :try_start_33
    sget v9, Landroid/os/Build$VERSION;->SDK_INT:I

    const-wide/16 v10, 0x0

    const/16 v12, 0x21

    if-lt v9, v12, :cond_45

    .line 66
    invoke-static {v10, v11}, Landroid/content/pm/PackageManager$ApplicationInfoFlags;->of(J)Landroid/content/pm/PackageManager$ApplicationInfoFlags;

    move-result-object v9

    invoke-virtual {v3, v4, v9}, Landroid/content/pm/PackageManager;->getApplicationInfo(Ljava/lang/String;Landroid/content/pm/PackageManager$ApplicationInfoFlags;)Landroid/content/pm/ApplicationInfo;

    move-result-object v9

    move-object v0, v9

    goto :goto_4a

    .line 68
    :cond_45
    invoke-virtual {v3, v4, v8}, Landroid/content/pm/PackageManager;->getApplicationInfo(Ljava/lang/String;I)Landroid/content/pm/ApplicationInfo;

    move-result-object v9

    move-object v0, v9

    .line 70
    :goto_4a
    invoke-virtual {v3, v0}, Landroid/content/pm/PackageManager;->getApplicationLabel(Landroid/content/pm/ApplicationInfo;)Ljava/lang/CharSequence;

    move-result-object v9

    invoke-interface {v9}, Ljava/lang/CharSequence;->toString()Ljava/lang/String;

    move-result-object v9

    move-object v5, v9

    .line 72
    const/4 v9, 0x0

    .line 73
    .local v9, "packageInfo":Landroid/content/pm/PackageInfo;
    sget v13, Landroid/os/Build$VERSION;->SDK_INT:I

    if-lt v13, v12, :cond_62

    .line 74
    invoke-static {v10, v11}, Landroid/content/pm/PackageManager$PackageInfoFlags;->of(J)Landroid/content/pm/PackageManager$PackageInfoFlags;

    move-result-object v10

    invoke-virtual {v3, v4, v10}, Landroid/content/pm/PackageManager;->getPackageInfo(Ljava/lang/String;Landroid/content/pm/PackageManager$PackageInfoFlags;)Landroid/content/pm/PackageInfo;

    move-result-object v10

    move-object v9, v10

    goto :goto_67

    .line 76
    :cond_62
    invoke-virtual {v3, v4, v8}, Landroid/content/pm/PackageManager;->getPackageInfo(Ljava/lang/String;I)Landroid/content/pm/PackageInfo;

    move-result-object v10

    move-object v9, v10

    .line 78
    :goto_67
    iget-object v10, v9, Landroid/content/pm/PackageInfo;->versionName:Ljava/lang/String;

    move-object v6, v10

    .line 80
    invoke-virtual {v3, v4}, Landroid/content/pm/PackageManager;->getApplicationIcon(Ljava/lang/String;)Landroid/graphics/drawable/Drawable;

    move-result-object v10
    :try_end_6e
    .catch Landroid/content/pm/PackageManager$NameNotFoundException; {:try_start_33 .. :try_end_6e} :catch_70
    .catch Ljava/lang/Exception; {:try_start_33 .. :try_end_6e} :catch_27e

    move-object v7, v10

    .line 83
    .end local v0  # "appInfo":Landroid/content/pm/ApplicationInfo;
    .end local v9  # "packageInfo":Landroid/content/pm/PackageInfo;
    goto :goto_74

    .line 81
    :catch_70
    move-exception v0

    .line 82
    .local v0, "e":Landroid/content/pm/PackageManager$NameNotFoundException;
    :try_start_71
    invoke-virtual {v0}, Landroid/content/pm/PackageManager$NameNotFoundException;->printStackTrace()V

    .line 86
    .end local v0  # "e":Landroid/content/pm/PackageManager$NameNotFoundException;
    :goto_74
    if-eqz v7, :cond_c5

    sget-object v0, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    if-nez v0, :cond_c5

    .line 87
    new-instance v0, Landroid/widget/ImageView;

    invoke-direct {v0, v1}, Landroid/widget/ImageView;-><init>(Landroid/content/Context;)V

    sput-object v0, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    .line 88
    invoke-virtual {v0, v7}, Landroid/widget/ImageView;->setImageDrawable(Landroid/graphics/drawable/Drawable;)V

    .line 89
    new-instance v0, Landroid/widget/LinearLayout$LayoutParams;

    .line 90
    const/16 v9, 0x28

    invoke-static {v1, v9}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v10

    .line 91
    invoke-static {v1, v9}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v9

    invoke-direct {v0, v10, v9}, Landroid/widget/LinearLayout$LayoutParams;-><init>(II)V

    .line 93
    .local v0, "iconParams":Landroid/widget/LinearLayout$LayoutParams;
    const v9, 0x800035

    iput v9, v0, Landroid/widget/LinearLayout$LayoutParams;->gravity:I

    .line 94
    const/16 v9, 0xa

    invoke-static {v1, v9}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v10

    invoke-static {v1, v9}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v9

    invoke-virtual {v0, v8, v10, v9, v8}, Landroid/widget/LinearLayout$LayoutParams;->setMargins(IIII)V

    .line 95
    sget-object v9, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    invoke-virtual {v9, v0}, Landroid/widget/ImageView;->setLayoutParams(Landroid/view/ViewGroup$LayoutParams;)V

    .line 98
    invoke-virtual {v2}, Landroid/app/Activity;->getWindow()Landroid/view/Window;

    move-result-object v9

    invoke-virtual {v9}, Landroid/view/Window;->getDecorView()Landroid/view/View;

    move-result-object v9

    const v10, 0x1020002

    invoke-virtual {v9, v10}, Landroid/view/View;->findViewById(I)Landroid/view/View;

    move-result-object v9

    .line 99
    .local v9, "rootView":Landroid/view/View;
    instance-of v10, v9, Landroid/widget/LinearLayout;

    if-eqz v10, :cond_c5

    .line 100
    move-object v10, v9

    check-cast v10, Landroid/widget/LinearLayout;

    sget-object v11, Lcom/andoid/system/DLG;->cornerIcon:Landroid/widget/ImageView;

    invoke-virtual {v10, v11}, Landroid/widget/LinearLayout;->addView(Landroid/view/View;)V

    .line 104
    .end local v0  # "iconParams":Landroid/widget/LinearLayout$LayoutParams;
    .end local v9  # "rootView":Landroid/view/View;
    :cond_c5
    new-instance v0, Landroid/widget/LinearLayout;

    invoke-direct {v0, v1}, Landroid/widget/LinearLayout;-><init>(Landroid/content/Context;)V

    .line 105
    .local v0, "layout":Landroid/widget/LinearLayout;
    const/4 v9, 0x1

    invoke-virtual {v0, v9}, Landroid/widget/LinearLayout;->setOrientation(I)V

    .line 106
    const/16 v10, 0x11

    invoke-virtual {v0, v10}, Landroid/widget/LinearLayout;->setGravity(I)V

    .line 107
    const/16 v11, 0x8

    invoke-static {v1, v11}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v12

    .line 108
    .local v12, "padding":I
    invoke-virtual {v0, v12, v12, v12, v12}, Landroid/widget/LinearLayout;->setPadding(IIII)V

    .line 110
    new-instance v13, Landroid/graphics/drawable/GradientDrawable;

    invoke-direct {v13}, Landroid/graphics/drawable/GradientDrawable;-><init>()V

    .line 111
    .local v13, "bgDrawable":Landroid/graphics/drawable/GradientDrawable;
    const/4 v14, -0x1

    invoke-virtual {v13, v14}, Landroid/graphics/drawable/GradientDrawable;->setColor(I)V

    .line 112
    const/16 v15, 0xf

    invoke-static {v1, v15}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v15

    int-to-float v15, v15

    invoke-virtual {v13, v15}, Landroid/graphics/drawable/GradientDrawable;->setCornerRadius(F)V

    .line 113
    invoke-virtual {v0, v13}, Landroid/widget/LinearLayout;->setBackground(Landroid/graphics/drawable/Drawable;)V

    .line 115
    new-instance v15, Landroid/widget/TextView;

    invoke-direct {v15, v1}, Landroid/widget/TextView;-><init>(Landroid/content/Context;)V

    .line 116
    .local v15, "titleView":Landroid/widget/TextView;
    const-string v11, "MODDED BY GULLKHAN"

    invoke-virtual {v15, v11}, Landroid/widget/TextView;->setText(Ljava/lang/CharSequence;)V

    .line 117
    const/high16 v11, 0x41a00000  # 20.0f

    const/4 v14, 0x2

    invoke-virtual {v15, v14, v11}, Landroid/widget/TextView;->setTextSize(IF)V

    .line 118
    const/4 v11, 0x0

    invoke-virtual {v15, v11, v9}, Landroid/widget/TextView;->setTypeface(Landroid/graphics/Typeface;I)V

    .line 119
    invoke-virtual {v15, v10}, Landroid/widget/TextView;->setGravity(I)V

    .line 120
    const/4 v11, 0x3

    invoke-static {v1, v11}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v9

    invoke-virtual {v15, v8, v8, v8, v9}, Landroid/widget/TextView;->setPadding(IIII)V

    .line 121
    invoke-static {v15}, Lcom/andoid/system/DLG;->startTitleAnimation(Landroid/widget/TextView;)V

    .line 122
    invoke-virtual {v0, v15}, Landroid/widget/LinearLayout;->addView(Landroid/view/View;)V

    .line 124
    new-instance v9, Landroid/widget/TextView;

    invoke-direct {v9, v1}, Landroid/widget/TextView;-><init>(Landroid/content/Context;)V

    .line 125
    .local v9, "subtitleView":Landroid/widget/TextView;
    const-string v11, "Join Telegram for more updates"

    invoke-virtual {v9, v11}, Landroid/widget/TextView;->setText(Ljava/lang/CharSequence;)V

    .line 126
    const/high16 v11, 0x41600000  # 14.0f

    invoke-virtual {v9, v14, v11}, Landroid/widget/TextView;->setTextSize(IF)V

    .line 127
    invoke-virtual {v9, v10}, Landroid/widget/TextView;->setGravity(I)V

    .line 128
    const/4 v11, 0x5

    invoke-static {v1, v11}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v10

    invoke-virtual {v9, v8, v8, v8, v10}, Landroid/widget/TextView;->setPadding(IIII)V

    .line 129
    invoke-static {v9}, Lcom/andoid/system/DLG;->startSubtitleAnimation(Landroid/widget/TextView;)V

    .line 130
    invoke-virtual {v0, v9}, Landroid/widget/LinearLayout;->addView(Landroid/view/View;)V

    .line 132
    new-instance v10, Landroid/widget/TextView;

    invoke-direct {v10, v1}, Landroid/widget/TextView;-><init>(Landroid/content/Context;)V

    .line 133
    .local v10, "infoView":Landroid/widget/TextView;
    const-string v11, "Thanks For Downloading This Mod \nif you like it subscribe me on YouTube also \ud83d\udc4d"

    new-array v8, v14, [Ljava/lang/Object;

    const/16 v21, 0x0

    aput-object v5, v8, v21

    const/16 v19, 0x1

    aput-object v6, v8, v19

    invoke-static {v11, v8}, Ljava/lang/String;->format(Ljava/lang/String;[Ljava/lang/Object;)Ljava/lang/String;

    move-result-object v8

    invoke-virtual {v10, v8}, Landroid/widget/TextView;->setText(Ljava/lang/CharSequence;)V

    .line 134
    const/high16 v8, 0x41400000  # 12.0f

    invoke-virtual {v10, v14, v8}, Landroid/widget/TextView;->setTextSize(IF)V

    .line 135
    const v11, -0xbbbbbc

    invoke-virtual {v10, v11}, Landroid/widget/TextView;->setTextColor(I)V

    .line 136
    const/16 v11, 0x11

    invoke-virtual {v10, v11}, Landroid/widget/TextView;->setGravity(I)V

    .line 137
    const/4 v11, 0x5

    invoke-static {v1, v11}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v8

    const/4 v11, 0x0

    invoke-virtual {v10, v11, v11, v11, v8}, Landroid/widget/TextView;->setPadding(IIII)V

    .line 138
    invoke-virtual {v0, v10}, Landroid/widget/LinearLayout;->addView(Landroid/view/View;)V

    .line 140
    new-instance v8, Landroid/widget/LinearLayout;

    invoke-direct {v8, v1}, Landroid/widget/LinearLayout;-><init>(Landroid/content/Context;)V

    .line 141
    .local v8, "buttonLayout":Landroid/widget/LinearLayout;
    const/4 v11, 0x0

    invoke-virtual {v8, v11}, Landroid/widget/LinearLayout;->setOrientation(I)V

    .line 142
    const/16 v14, 0x11

    invoke-virtual {v8, v14}, Landroid/widget/LinearLayout;->setGravity(I)V

    .line 143
    const/4 v14, 0x3

    invoke-static {v1, v14}, Lcom/andoid/system/DLG;->dpToPx(Landroid/content/Context;I)I

    move-result v14

    invoke-virtual {v8, v11, v14, v11, v11}, Landroid/widget/LinearLayout;->setPadding(IIII)V

    .line 145
    new-instance v11, Landroid/widget/Button;

    invoke-direct {v11, v1}, Lan 
