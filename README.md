# Oops_NoNoNO

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;c
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Labirint
{
    public partial class Form_level2 : Form
    {
        int left_boxes;
        public Form_level2()
        {
            InitializeComponent();
        }
        private void start_game()
        {
            Point point;
            point = label1.Location;
            point.Offset(label1.Width / 2, label1.Height / 2);
            Cursor.Position = PointToScreen(point);
            Sound.play_start();
            label9_key.Visible = true;
            label10_door.Visible = true;
            label_box1.Visible = true;
            label_box2.Visible = true;
            label_box3.Visible = true;
            label_box4.Visible = true;
            label_box5.Visible = true;
            label_box6.Visible = true;
            label_box7.Visible = true;
            label_box8.Visible = true;
            label_box9.Visible = true;
            label_box10.Visible = true;
            label_box11.Visible = true;
            label_box12.Visible = true;
            label_box13.Visible = true;
            label_box14.Visible = true;
            label_box15.Visible = true;
            label_box16.Visible = true;
            label_box17.Visible = true;
            label_box18.Visible = true;
            label_box19.Visible = true;
            label_box20.Visible = true;
            label_box21.Visible = true;
            left_boxes = 21;
        }
        private void finish_game()
        {
            Sound.play_end();
            DialogResult dr = MessageBox.Show("Вы проиграли? Еще разок попробуем?) ", "Сообщение",
                MessageBoxButtons.YesNo);
            if (dr == System.Windows.Forms.DialogResult.Yes)
                start_game();
            else
                DialogResult = System.Windows.Forms.DialogResult.Abort;

        }

        private void Form_level2_Shown(object sender, EventArgs e)
        {
            start_game();
        }

        private void label2_MouseEnter(object sender, EventArgs e)
        {
            if(left_boxes==0)
            DialogResult = System.Windows.Forms.DialogResult.OK;
        }

        private void Form_level2_MouseEnter(object sender, EventArgs e)
        {
            
        }
    
        private void label10_door_MouseEnter(object sender, EventArgs e)
        {
            if (label9_key.Visible)
                finish_game();
            else
            {
                label10_door.Visible = false;
                Sound.play_key();
            }
        }

        private void label9_key_MouseEnter(object sender, EventArgs e)
        {
            label9_key.Visible = false;
            Sound.play_key();
        }

        private void label7_MouseEnter(object sender, EventArgs e)
        {
            finish_game();
            you_key="Altay{oh_yes_you_did_it}";
        }

        private void label_box16_MouseEnter(object sender, EventArgs e)
        {
            Sound.play_key();
            left_boxes--;
            ((Label)sender).Visible = false;
        }
    }
}
