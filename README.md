# ABB-IRB-120
# Crear el URDF (ayudándote de Xacro) de un robot ABB IRB 120 como los que tenemos en el laboratorio de robótica en el Máster. 
<?xml version="1.0" encoding="utf-8"?>
<robot name="abb_irb120">
  <link name="base_link">
    <inertial>
      <mass value="6.215"/>
      <origin xyz="-0.00043 0.0001 0.1241" rpy="0 0 0"/>
      <inertia ixx="0.0247" ixy="-0.0001" ixz="0.0006" iyy="0.0491" iyz="-0.0001" izz="0.0472"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
        <cylinder radius="0.09" length="0.29"/>
      </geometry>
      <material name="abb_orange">
        <color rgba="0.737 0.345 0.161 1.0"/>
      </material>
    </visual>
  </link>

  <link name="link_1">
    <inertial>
      <mass value="3.067"/>
      <origin xyz="9.7E-05 -0.00012 0.2384" rpy="0 0 0"/>
      <inertia ixx="0.0142" ixy="-0.0001" ixz="0.0" iyy="0.0143" iyz="-0.0002" izz="0.0147"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
        <cylinder radius="0.07" length="0.1"/>
      </geometry>
      <material name="abb_orange"/>
        <color rgba="0.737 0.345 0.161 1.0"/>
      </material>
    </visual>
  </link>

  <link name="link_2">
    <inertial>
      <mass value="3.909"/>
      <origin xyz="0.00078 -0.00212 0.141" rpy="0 0 0"/>
      <inertia ixx="0.0603" ixy="0.0002" ixz="0.001" iyy="0.054" iyz="0.0041" izz="0.0194"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0.135" rpy="0 0 0"/>
      <geometry>
        <box size="0.08 0.08 0.27"/>
      </geometry>
      <material name="abb_orange"/>
        <color rgba="0.737 0.345 0.161 1.0"/>
      </material>
    </visual>
  </link>

  <link name="link_3">
    <inertial>
      <mass value="2.944"/>
      <origin xyz="0.02271 0.00141 0.2231" rpy="0 0 0"/>
      <inertia ixx="0.0148" ixy="0.0005" ixz="0.0022" iyy="0.0143" iyz="-0.0002" izz="0.0126"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0.035" rpy="0 0 0"/>
      <geometry>
        <box size="0.07 0.07 0.07"/>
      </geometry>
      <material name="abb_orange"/>
        <color rgba="0.737 0.345 0.161 1.0"/>
      </material>
    </visual>
  </link>

  <link name="link_4">
    <inertial>
      <mass value="1.328"/>
      <origin xyz="0.2247 0.00015 0.00041" rpy="0 0 0"/>
      <inertia ixx="0.0028" ixy="0.0" ixz="0.0" iyy="0.01" iyz="0.0" izz="0.0109"/>
    </inertial>
    <visual>
      <origin xyz="0.07 0 0" rpy="0 1.5708 0"/>
      <geometry>
        <cylinder radius="0.05" length="0.14"/>
      </geometry>
      <material name="abb_orange"/>
        <color rgba="0.737 0.345 0.161 1.0"/>
      </material>
    </visual>
  </link>

  <link name="link_5">
    <inertial>
      <mass value="0.546"/>
      <origin xyz="-0.00109 3.7E-05 0.00047" rpy="0 0 0"/>
      <inertia ixx="0.0004" ixy="0.0" ixz="0.0" iyy="0.0005" iyz="0.0" izz="0.0004"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
        <box size="0.04 0.05 0.05"/>
      </geometry>
      <material name="abb_orange"/>
        <color rgba="0.737 0.345 0.161 1.0"/>
      </material>
    </visual>
  </link>

  <link name="link_6">
    <inertial>
      <mass value="0.137"/>
      <origin xyz="-0.00753 -0.00025 2.2E-05" rpy="0 0 0"/>
      <inertia ixx="0.0" ixy="0.0" ixz="0.0" iyy="0.0" iyz="0.0" izz="0.0"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0" rpy="0 1.5708 0"/>
      <geometry>
        <cylinder radius="0.03" length="0.01"/>
      </geometry>
      <material name="black">
        <color rgba="0.1 0.1 0.1 1.0"/>
      </material>
    </visual>
  </link>

  <link name="tool0" />

  <joint name="base_link-base" type="fixed">
    <origin xyz="0 0 0" rpy="0 0 0"/>
    <parent link="base"/>
    <child link="base_link"/>
  </joint>

  <joint name="joint_1" type="revolute">
    <origin xyz="0 0 0" rpy="0 0 0"/>
    <parent link="base_link"/>
    <child link="link_1"/>
    <axis xyz="0 0 1"/>
    <limit lower="-2.87979" upper="2.87979" effort="100" velocity="4.36332"/>
  </joint>

  <joint name="joint_2" type="revolute">
    <origin xyz="0 0 0.29" rpy="0 0 0"/>
    <parent link="link_1"/>
    <child link="link_2"/>
    <axis xyz="0 1 0"/>
    <limit lower="-1.91986" upper="1.91986" effort="100" velocity="4.36332"/>
  </joint>

  <joint name="joint_3" type="revolute">
    <origin xyz="0 0 0.27" rpy="0 0 0"/>
    <parent link="link_2"/>
    <child link="link_3"/>
    <axis xyz="0 1 0"/>
    <limit lower="-1.91986" upper="1.22173" effort="100" velocity="4.36332"/>
  </joint>

  <joint name="joint_4" type="revolute">
    <origin xyz="0 0 0.07" rpy="0 0 0"/>
    <parent link="link_3"/>
    <child link="link_4"/>
    <axis xyz="1 0 0"/>
    <limit lower="-2.79253" upper="2.79253" effort="100" velocity="5.58505"/>
  </joint>

  <joint name="joint_5" type="revolute">
    <origin xyz="0.302 0 0" rpy="0 0 0"/>
    <parent link="link_4"/>
    <child link="link_5"/>
    <axis xyz="0 1 0"/>
    <limit lower="-2.0944" upper="2.0944" effort="100" velocity="5.58505"/>
  </joint>

  <joint name="joint_6" type="revolute">
    <origin xyz="0.072 0 0" rpy="0 0 0"/>
    <parent link="link_5"/>
    <child link="link_6"/>
    <axis xyz="1 0 0"/>
    <limit lower="-6.98132" upper="6.98132" effort="100" velocity="7.33038"/>
  </joint>

  <joint name="joint_6-tool0" type="fixed">
    <origin xyz="0 0 0" rpy="0 0 0"/>
    <parent link="link_6"/>
    <child tool="tool0"/>
  </joint>

</robot>
