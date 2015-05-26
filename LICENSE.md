using System;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Finish : Form
    {
        public Finish()
        {
            InitializeComponent();
            Sound.PlayVictory();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;

            StartMenu();
        }
        private void StartMenu()
        {
            Menu mn = new Menu();
            mn.ShowDialog();
        }
    }
}

using System;
using System.Drawing;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Lvl1 : Form
    {
        public Lvl1()
        {
            InitializeComponent();
            Sound.PlayStart();
          
        }

        private void MouseStartLocation()
        {
            Point point;
            point = lableStart.Location;
            point.Offset(lableStart.Width / 2, lableStart.Height / 2);
            Cursor.Position = PointToScreen(point);
        }

        private void Lvl1_Shown(object sender, EventArgs e)
        {
            MouseStartLocation();
        }

        private void labelFinish_MouseEnter(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;
            StartLvl2();
        }
        private void StartLvl2()
        {
            Lvl2 level2 = new Lvl2();
            level2.ShowDialog();
        }

        private void PlayFail()
        {
            Sound.PlayFail();
           DialogResult dr =  MessageBox.Show("Ты проиграл, еще разок?","",MessageBoxButtons.YesNo);
           if (dr == System.Windows.Forms.DialogResult.Yes)
           {
               MouseStartLocation();
           }
           else
           {
               DialogResult = System.Windows.Forms.DialogResult.Abort;
           }
        }

        private void label2_MouseEnter(object sender, EventArgs e)
        {
            PlayFail();
        }    
    }
}

using System;
using System.Drawing;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Lvl2 : Form
    {
        public Lvl2()
        {
            InitializeComponent();
            Sound.PlayStart();
        }

        private void MouseStartLocation()
        {
            Point point;
            point = lableStart.Location;
            point.Offset(lableStart.Width / 2, lableStart.Height / 2);
            labelDoor.Visible = true;
            lableKey.Visible = true;
            Cursor.Position = PointToScreen(point);
        }

      
        private void PlayFail()
        {
            Sound.PlayFail();
            DialogResult dr = MessageBox.Show("Ты проиграл, еще разок?", "", MessageBoxButtons.YesNo);
            if (dr == System.Windows.Forms.DialogResult.Yes)
            {
                MouseStartLocation();
            }
            else
            {
                DialogResult = System.Windows.Forms.DialogResult.Abort;
            }
        }

        private void Lvl2_Shown(object sender, EventArgs e)
        {
            MouseStartLocation();
        }

       

        private void lableKey_MouseEnter(object sender, EventArgs e)
        {
            lableKey.Visible = false;
            Sound.PlayKey();
            
        }

        private void label3_MouseEnter(object sender, EventArgs e)
        {
            PlayFail();
        }

        private void labelDoor_MouseEnter(object sender, EventArgs e)
        {
            if (lableKey.Visible == false)
            {
                labelDoor.Visible = false;
                Sound.PlayKey();
            }
            else
            {
                PlayFail();
            }

        }

        private void labelFinish_MouseEnter(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;
            StartLvl3();

        }

        private void StartLvl3()
        {
            Lvl3 level3 = new Lvl3();
            level3.ShowDialog();
        }
    }
}
using System;
using System.Drawing;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Lvl3 : Form
    {
        public Lvl3()
        {
            InitializeComponent();
            Sound.PlayStart();
        }
        private void MouseStartLocation()
        {
            Point point;
            point = lableStart.Location;
            point.Offset(lableStart.Width / 2, lableStart.Height / 2);
            Cursor.Position = PointToScreen(point);
            label_wall1.Visible = true;
            label_wall2.Visible = false;
            label_wall3.Visible = true;
            label_wall4.Visible = false;
            label_wall5.Visible = true;
            label_wall6.Visible = false;
            label_wall7.Visible = true;
        }
        private void PlayFail()
        {
            Sound.PlayFail();
            DialogResult dr = MessageBox.Show("Ты проиграл, еще разок?", "", MessageBoxButtons.YesNo);
            if (dr == System.Windows.Forms.DialogResult.Yes)
            {
                MouseStartLocation();
            }
            else
            {
                DialogResult = System.Windows.Forms.DialogResult.Abort;
            }
        }

        private void Lvl3_Shown(object sender, EventArgs e)
        {
            MouseStartLocation();
        }

        private void label3_MouseEnter(object sender, EventArgs e)
        {
            PlayFail();

        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            label_wall1.Visible = !label_wall1.Visible;
            label_wall2.Visible = !label_wall2.Visible;
            label_wall3.Visible = !label_wall3.Visible;
            label_wall4.Visible = !label_wall4.Visible;
            label_wall5.Visible = !label_wall5.Visible;
            label_wall6.Visible = !label_wall6.Visible;
            label_wall7.Visible = !label_wall7.Visible;
        }

        private void labelFinish_MouseEnter(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;
            StartLvl4();

        }

        private void StartLvl4()
        {
            Lvl4 level4 = new Lvl4();
            level4.ShowDialog();
        }
    }
}

using System;
using System.Drawing;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Lvl4 : Form
    {
        public Lvl4()
        {
            InitializeComponent();
            Sound.PlayStart();
        }

        private void MouseStartLocation()
        {
            Point point;
            point = lableStart.Location;
            point.Offset(lableStart.Width / 2, lableStart.Height / 2);
            Cursor.Position = PointToScreen(point);
            YelowKey.Visible = true;
            YelowDoor.Visible = true;
            labelWall1.Visible = true;
            labelWall2.Visible = false;
            labelWall3.Visible = true;
            wall20.Visible = true;
            labelWall5.Visible = true;
            labelWall6.Visible = false;
        }


        private void PlayFail()
        {
            Sound.PlayFail();
            DialogResult dr = MessageBox.Show("Ты проиграл, еще разок?", "", MessageBoxButtons.YesNo);
            if (dr == System.Windows.Forms.DialogResult.Yes)
            {
                MouseStartLocation();
            }
            else
            {
                DialogResult = System.Windows.Forms.DialogResult.Abort;
            }
        }

        private void label3_MouseEnter(object sender, EventArgs e)
        {
            PlayFail();
        }

        private void YelowKey_MouseEnter(object sender, EventArgs e)
        {
            YelowKey.Visible = false;
            Sound.PlayKey();
        }

        private void YelowDoor_MouseEnter(object sender, EventArgs e)
        {
            if (YelowKey.Visible == false)
            {
                YelowDoor.Visible = false;
                Sound.PlayKey();
            }
            else 
            {
                PlayFail();
            }

        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            labelWall1.Visible = !labelWall1.Visible;
            labelWall2.Visible = !labelWall2.Visible;
            labelWall3.Visible = !labelWall3.Visible;
            wall20.Visible = !wall20.Visible;
            labelWall5.Visible = !labelWall5.Visible;
            labelWall6.Visible = !labelWall6.Visible;
        }

        private void RedKey_MouseEnter(object sender, EventArgs e)
        {
            RedKey.Visible = false;
            Sound.PlayKey();
        }

        private void timer2_Tick(object sender, EventArgs e)
        {
            if (RedKey.Visible == false)
            {
                redDoor1.Visible = !redDoor1.Visible;
                redDoor2.Visible = !redDoor2.Visible;
            }
        }

        private void labelFinish_MouseEnter(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;

            StartLvl5();
        }
        private void StartLvl5()
        {
            Lvl5 level5 = new Lvl5();
            level5.ShowDialog();
        }

        private void Lvl4_Shown(object sender, EventArgs e)
        {
            MouseStartLocation();
        }
    }
}


using System;
using System.Drawing;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Lvl5 : Form
    {
        public Lvl5()
        {
            InitializeComponent();
            Sound.PlayStart();
        }

        private void label3_MouseEnter(object sender, EventArgs e)
        {
            PlayFail();
        }
        private void MouseStartLocation()
        {
            Point point;
            point = lableStart.Location;
            point.Offset(lableStart.Width / 2, lableStart.Height / 2);
            Cursor.Position = PointToScreen(point);
            YelowKey.Visible = true;
            RedKey.Visible = true;
            YellowDoor2.Visible = true;
            YellowDoor1.Visible = true;
            RedDoor1.Visible = true;
            RedDoor2.Visible = true;
            labelwall1.Visible = true;
            labelwall2.Visible = false;
            labelwall3.Visible = true;
            labelwall4.Visible = false;
            labelwall5.Visible = true;
            labelwall6.Visible = false;
            labelwall7.Visible = true;
            labelwall8.Visible = false;
            labelwall9.Visible = true;
            labelwall10.Visible = false;
            labelwall11.Visible = true;
            labelwall13.Visible = false;
            labelwall15.Visible = true;
            labelwall16.Visible = false;
            labelwall17.Visible = true;
            labelwall18.Visible = false;
            labelwall1.Visible = true;
            RedDoor1.Visible = true;
            RedDoor2.Visible = true;
            
        }

        private void PlayFail()
        {
            Sound.PlayFail();
            DialogResult dr = MessageBox.Show("Ты проиграл, еще разок?", "", MessageBoxButtons.YesNo);
            if (dr == System.Windows.Forms.DialogResult.Yes)
            {
                MouseStartLocation();
            }
            else
            {
                DialogResult = System.Windows.Forms.DialogResult.Abort;
            }
        }

        private void YelowKey_MouseEnter(object sender, EventArgs e)
        {
            YelowKey.Visible = false;
            Sound.PlayKey();
        }

        
        private void YellowDoor1_MouseEnter(object sender, EventArgs e)
        {
            if (YelowKey.Visible == false)
            {
                YellowDoor1.Visible = false;
                YellowDoor2.Visible = false;
            }
            else 
            {
                Sound.PlayFail();
            }
        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            labelwall1.Visible = !labelwall1.Visible;
            labelwall2.Visible = !labelwall2.Visible;
            labelwall3.Visible = !labelwall3.Visible;
            labelwall4.Visible = !labelwall4.Visible;
            labelwall5.Visible = !labelwall5.Visible;
            labelwall6.Visible = !labelwall6.Visible;
            labelwall7.Visible = !labelwall7.Visible;
            labelwall8.Visible = !labelwall8.Visible;
            labelwall9.Visible = !labelwall9.Visible;
            labelwall10.Visible = !labelwall10.Visible;
            labelwall11.Visible = !labelwall11.Visible;
            labelwall13.Visible = !labelwall13.Visible;
            labelwall15.Visible = !labelwall15.Visible;
            labelwall16.Visible = !labelwall16.Visible;
            labelwall17.Visible = !labelwall17.Visible;
            labelwall18.Visible = !labelwall18.Visible;
            labelwall19.Visible = !labelwall19.Visible;
       
        }

        private void timer2_Tick(object sender, EventArgs e)
        {
            if (RedKey.Visible == false)
            {
                RedDoor1.Visible = !RedDoor1.Visible;
                RedDoor2.Visible = !RedDoor2.Visible;
            }
        }

        private void Lvl5_Shown(object sender, EventArgs e)
        {
            MouseStartLocation();
        }

        private void labelFinish_MouseEnter(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;
            StartFinish();

        }

        private void StartFinish()
        {
            Finish fin = new Finish();
            fin.ShowDialog();
        }

        private void RedKey_MouseEnter(object sender, EventArgs e)
        {
            RedKey.Visible = false;
            Sound.PlayKey();
        }


       
    }
}
using System;
using System.Windows.Forms;

namespace CrazyArrow
{
    static class Program
    {
        /// <summary>
        /// The main entry point for the application.
        /// </summary>
        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.SetCompatibleTextRenderingDefault(false);
            Application.Run(new Menu());
        }
    }
}
using System;
using System.Windows.Forms;

namespace CrazyArrow
{
    public partial class Rules : Form
    {
        public Rules()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            DialogResult = System.Windows.Forms.DialogResult.Abort;

            StartMenu();
        }
        private void StartMenu()
        {
            Menu mn = new Menu();
            mn.ShowDialog();
        }
    }
}

using System.Media;
using WMPLib;

namespace CrazyArrow
{
    static class Sound
    {
        static SoundPlayer sound_Fail = new SoundPlayer(Properties.Resources.sound_fail);
        static SoundPlayer sound_Key = new SoundPlayer(Properties.Resources.sound_key);
        static WindowsMediaPlayer sound_Start = new WindowsMediaPlayer();
        static WindowsMediaPlayer sound_Victory = new WindowsMediaPlayer();
        static bool sound_enabled = true;

        public static void SoundOn()
        {
            sound_enabled = true;
        }
        public static void SoundOff()
        {
            sound_enabled = false;
        }

        public static void PlayFail()
        {
            if (sound_enabled == true)
            {
                sound_Fail.Play();
            }
        }

        public static void PlayKey()
        {
            if (sound_enabled == true)
            {
                sound_Key.Play();
            }
        }
        public static void PlayStart()
        {
            sound_Start.URL = @"E:\Универ\ОП\Projects\Курсач\CrazyArrow\CrazyArrow\Resources\Zasekrecheno-Koncovka_iz_Spanch_Boba.mp3";
            if (sound_enabled == true)
            {
                
                sound_Start.controls.play();
            }
            else
            {
                sound_Start.controls.stop();
            }
        }
       

        public static void PlayVictory()
        {
            if (sound_enabled == true)
            {
                sound_Victory.URL = @"E:\Универ\ОП\Projects\Курсач\CrazyArrow\CrazyArrow\Resources\Final.mp3";
            }
        }
    }
}

